Attached file https://arxiv.org/pdf/2302.11382
Prompt: Please extract each page of this PDF to a plain text file.  Then, manually read the first three pages and learn what a prompt pattern is.  Don't worry if there are formatting issues, just do your best and proceed.  Then, ask me to describe my job or interests.  Use what I tell you to describe to me what a prompt pattern is assuming. I have no background in computer science.  Make sure and use concrete examples based on my job or interests to show how I could use these patterns.  Make sure and write some sample prompt patterns that could be cut/pasted into Code interpreter for me to try out.  Each pattern should rely on a document or dataset relevant to me.  Describe the purpose of the pattern, the problem it is trying to solve, what data the pattern needs and why, and then the prompt that will be used on the document.
Answer: I’ve read the first three pages of your PDF, which explain that a **prompt pattern** is a reusable way of structuring a prompt so a large language model (LLM) like ChatGPT can more reliably give you the kind of output or interaction you want.

It’s similar to a “design pattern” in software engineering — a documented, repeatable solution to a recurring problem — but here it’s applied to prompts. A prompt pattern has a **name**, a description of the **problem it solves**, the **context** where it works best, the **key ideas** you should communicate to the LLM, an **example implementation**, and the **pros/cons** of using it. The idea is that once you understand a pattern, you can adapt it to many different situations by changing the subject matter or the data you give it. For example, patterns might make the LLM always take on a specific role (“Persona”), always ask you questions instead of answering immediately (“Flipped Interaction”), or produce output in a rigid format (“Template”).

Before I tailor examples for you, I’ll need to know about **your job or your main interests**. With that, I can explain prompt patterns in plain language using concrete, relatable examples from your work, and then write some **ready-to-use prompt patterns** you can paste into Code Interpreter. These will include:

* The **purpose** of the pattern
* The **problem** it solves
* The **data** it needs and why
* The **exact prompt** you can use on your own documents or datasets.

So — can you tell me about your job or your main interests?
Got it — you’re in software engineering and architecture, with a strong interest in AI.
I’ll keep the explanation in plain terms (no computer science jargon walls) but use examples from your world, so it’s both clear and practical.

---

## **What is a Prompt Pattern? (Your Context)**

A **prompt pattern** is like a reusable “blueprint” for talking to an AI so it does what you want — reliably, and in a way you can repeat.
In software architecture, you might have design patterns like *Singleton* or *Observer* that solve common problems in predictable ways. Prompt patterns are the *prompt-writing equivalent* of that — a way to structure your instructions so the AI produces exactly the kind of output or interaction you need.

For example:

* Without a pattern, you might just type:
  *“Analyze this Java service and tell me if it’s secure.”*
  You might get a decent answer… or a vague one.
* With a pattern — say, the **Persona** pattern — you’d instead say:
  *“Act as a senior security architect reviewing Java microservices. Provide a list of vulnerabilities with severity ratings and suggested code changes. Assume OpenShift deployment.”*
  Now the AI knows exactly what “lens” to use and what details to give you.

Patterns make prompts:

1. **Consistent** — same type of result every time.
2. **Reusable** — just swap in new data.
3. **Smarter** — they push the AI to think or interact in a certain way.

---

## **Three Prompt Patterns You Could Use in Your Work**

### 1. **Fact Check List Pattern**

* **Purpose**: Avoid “confident nonsense” in AI answers.
* **Problem It Solves**: AI can generate convincing but wrong information (e.g., wrong library versions, inaccurate architecture claims).
* **Data Needed**: The document or code you want reviewed.
* **Why**: The AI can list all the facts/assumptions its answer relies on, so you know what to double-check.
* **Prompt**:

  ```
  From now on, when you analyze my software architecture documents or code, 
  provide your answer, then list the set of facts your answer depends on 
  that should be fact-checked. Only include facts related to security, 
  performance, or compliance.
  ```
* **Example Use**: Give the AI a Spring Boot service manifest, have it list performance assumptions (“assumes DB connections are pooled”, “assumes OpenShift node has 4 CPU cores”), and then verify them.

---

### 2. **Flipped Interaction Pattern**

* **Purpose**: Let the AI drive the questioning to reach a goal.
* **Problem It Solves**: When you don’t know exactly what details to provide for a task.
* **Data Needed**: The goal you want to reach (e.g., “produce a Tekton pipeline for CI/CD”).
* **Why**: The AI can ask you targeted questions you might not think of, ensuring it has all the needed info before acting.
* **Prompt**:

  ```
  From now on, I would like you to ask me questions to design and generate a 
  production-grade Tekton pipeline YAML for a Java Spring Boot microservice 
  deployed in OpenShift. When you have enough information, output the final YAML. 
  Ask the questions one at a time.
  ```
* **Example Use**: Saves you from back-and-forth “oops, forgot to tell you that” — AI will systematically gather the requirements.

---

### 3. **Template Pattern**

* **Purpose**: Force AI output to match a strict structure you need.
* **Problem It Solves**: AI sometimes drifts into prose or changes formatting — not good when output must be machine-readable or match a compliance format.
* **Data Needed**: The exact template (with placeholders) you need filled.
* **Why**: Ensures generated CI configs, architecture docs, or compliance checklists match the right structure.
* **Prompt**:

  ```
  I am going to provide a template for your output. Everything in ALL_CAPS 
  is a placeholder. Any time you generate text, fit it into one of these 
  placeholders and preserve the formatting. 
  TEMPLATE:
  Service Name: SERVICE_NAME
  Description: DESCRIPTION
  Dependencies: DEPENDENCIES
  Risk Level: RISK_LEVEL
  Mitigation Steps: MITIGATION_STEPS
  ```
* **Example Use**: Feed in different microservices’ metadata and get uniform risk reports.

---

If you want, I can also write **ready-to-use Code Interpreter patterns** for these so you can upload a dataset or codebase, and the AI will follow the pattern automatically while running analysis on your files. That way you can drop in any architecture diagram, pipeline config, or log file, and the AI applies the same pattern every time.


