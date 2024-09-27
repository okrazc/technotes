Deploying a Spring Boot Application to Pivotal Cloud Foundry (PCF)

This guide covers all the essential steps a developer needs to know when deploying a Spring Boot application to Pivotal Cloud Foundry (PCF). It includes details on setting up the environment, preparing the application, creating necessary configurations, and using key Cloud Foundry (CF) commands.

---

### 1. **Setting up PCF (Pivotal Cloud Foundry) Environment**

#### Step 1: Install the Cloud Foundry CLI
You’ll need the **CF CLI** to interact with PCF. Download it from [Cloud Foundry’s website](https://docs.cloudfoundry.org/cf-cli/install-go-cli.html).

Once installed, verify the installation:
```bash
cf --version
```

#### Step 2: Log in to the PCF Cluster
To deploy your Spring Boot application, you need to log in to your PCF instance. Use the **`cf login`** command and provide your credentials and the **API endpoint** of the target cluster.

```bash
cf login -a https://api.example-cloud.com
```
- **API endpoint**: The URL of the PCF environment.
- **Org**: Logical group that represents a company or division.
- **Space**: A smaller unit inside an Org, used for app isolation (e.g., dev, staging, production).

Example:
```bash
cf login
API endpoint: https://api.example-cloud.com
Email> your.email@example.com
Password> ********
```

After logging in, target the correct **Org** and **Space**:
```bash
cf target -o <your-org> -s <your-space>
```

---

### 2. **Preparing the Spring Boot Application**

#### Step 1: Build the Application
Before deploying, you need to build your Spring Boot application into a **JAR** or **WAR** file.

- **For Maven:**
  ```bash
  mvn clean package
  ```
  This will generate a JAR file in the `target/` directory, e.g., `target/spring-boot-app.jar`.

- **For Gradle:**
  ```bash
  ./gradlew build
  ```
  This will generate a JAR file in the `build/libs/` directory, e.g., `build/libs/spring-boot-app.jar`.

---

### 3. **Creating the Manifest File**

The **`manifest.yml`** file defines the configuration for deploying your application to PCF. Place this file in the root directory of your project.

#### Example `manifest.yml` for a Spring Boot Application Using JDK 17:
```yaml
applications:
  - name: spring-boot-app       # Application name
    memory: 1G                  # Memory allocation
    instances: 1                # Number of app instances
    path: target/spring-boot-app.jar  # Path to the JAR file (built from Maven or Gradle)
    buildpacks:
      - java_buildpack          # Specifies the Java buildpack
    env:
      JBP_CONFIG_OPEN_JDK_JRE: '{ jre: { version: 17.+ } }'  # Use JDK 17
    services:
      - my-database             # Any services (e.g., databases) that need binding
    routes:
      - route: spring-boot-app.example-cloud.com  # Define custom route/URL
```

### Key Elements of `manifest.yml`:
1. **`name`**: The name of the application that will be deployed.
2. **`memory`**: Specifies the memory allocated to the application. Adjust based on the needs of your app.
3. **`instances`**: Defines the number of instances to run. You can scale horizontally by increasing this value.
4. **`path`**: The path to the JAR (or WAR) file that was built from Maven/Gradle.
5. **`buildpacks`**: PCF uses buildpacks to automatically detect, build, and run your app. The `java_buildpack` is used for Java apps.
6. **`env`**: Environment variables to configure the runtime. In this case, it specifies the JDK version (e.g., 17).
7. **`services`**: This is where you define any services (e.g., databases) that your app will bind to. PCF supports service binding natively.
8. **`routes`**: Specify the URL or route where the app will be accessible.

---

### 4. **Deploying the Spring Boot Application**

#### Step 1: Push the Application
To deploy your app, run the **`cf push`** command. This command reads from the **`manifest.yml`** file and automates the deployment process.

```bash
cf push
```

- **What happens**:
  1. PCF uses the buildpack to compile and package the application into a container.
  2. The container is deployed to the PCF cloud.
  3. PCF orchestrates the application by managing scaling, networking, and routing.

You can specify the **`manifest.yml`** file explicitly if it's not in the current directory:
```bash
cf push -f /path/to/manifest.yml
```

#### Step 2: Verify Deployment
Once the application is deployed, you can verify it using the **`cf apps`** command:
```bash
cf apps
```
This will list all the deployed apps along with their state and URL.

---

### 5. **Managing and Scaling the Application**

#### View Logs:
You can check the logs for your application by running:
```bash
cf logs <app-name> --recent
```

#### Scale the Application:
You can increase or decrease the number of instances running using the **`cf scale`** command:
```bash
cf scale <app-name> -i 3  # Example: Scale to 3 instances
```

#### Bind/Unbind Services:
To bind a new service (e.g., a database) to your app:
```bash
cf bind-service <app-name> <service-name>
cf restage <app-name>  # Restage after binding new services
```

---

### 6. **Additional Configuration for Spring Boot**

#### Application Properties:
In a typical Spring Boot app, you should ensure that the application listens on the port provided by PCF. This can be configured in the **`application.yml`** or **`application.properties`** file:

```yaml
server:
  port: ${PORT:8080}  # PCF dynamically assigns the port
```

#### Spring Actuator (Optional):
Spring Boot Actuator is useful for health checks, metrics, and monitoring in PCF. You can include it in your `pom.xml`:
```xml
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-actuator</artifactId>
</dependency>
```

#### Logging:
PCF automatically captures logs, so no additional logging configuration is needed for basic deployments. However, you can integrate with log management tools if required.

---

### 7. **Other Useful CF Commands**

- **Stop/Start an app**:
  ```bash
  cf stop <app-name>
  cf start <app-name>
  ```

- **Delete an app**:
  ```bash
  cf delete <app-name>
  ```

- **Check app health**:
  ```bash
  cf app <app-name>
  ```

---
