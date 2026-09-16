## `examples/sample-questions.md`

```markdown
# Sample Questions

The following questions can be used to test the AI Document Agent after documents have been ingested into the vector store.

## 📄 General Document Questions

```text
What is this document about?
Summarize the main points of the document.
What are the key requirements mentioned in the document?
What are the important conditions mentioned?
🔍 Information Retrieval
What are the eligibility criteria mentioned in the document?
What documents or information are required?
What limitations are mentioned?
What exceptions are mentioned in the document?
What numerical limits are specified?
🧠 Contextual Questions

These questions can be used to test conversational memory.

Question 1
What is the document about?
Question 2
What is the most important requirement?
Question 3
Why is that requirement important?

The later questions depend on the context of the previous conversation.

🔎 Comparison Questions
What is the difference between the two eligibility conditions?
Compare the requirements mentioned in the document.
Which conditions apply to different categories of applicants?
📊 Analytical Questions
What are the main factors that determine eligibility?
What conditions could prevent an applicant from qualifying?
What are the most important rules mentioned in the document?
🧪 RAG Testing Questions
Direct Retrieval
What is the minimum requirement mentioned in the document?
Semantic Retrieval
What conditions must someone satisfy to qualify?
Specific Detail
What numerical limits are specified?
Multi-Part Question
What are the eligibility requirements and what exceptions are mentioned?
❌ Out-of-Context Testing

These questions can be used to test how the system behaves when information is not available in the connected documents.

What is the population of Japan?
Who is the current CEO of Google?
What is the weather today?

The expected behavior is for the system to avoid presenting unsupported document-based information when the answer cannot be found in the connected knowledge source.

⭐ Recommended Demo Questions

For demonstrating the project on GitHub, use questions that clearly show the RAG capability:

What is this document about?
What are the eligibility criteria mentioned in the document?
What are the minimum and maximum requirements?
Are there any exceptions mentioned?
Summarize the document in simple terms.