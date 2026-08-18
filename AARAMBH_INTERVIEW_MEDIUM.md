# AARAMBH AI — TECHNICAL INTERVIEW QUESTIONS
# MEDIUM SET — 25 QUESTIONS

---

## Q1. Explain the complete request flow in Aarambh.

### Answer

When a candidate submits an answer, the frontend sends it to
the backend. The backend authenticates and validates the
request, prepares the required context, sends it to the AI
layer, validates the generated result, stores it, and returns
the response to the frontend.

### Explanation

Frontend
    ↓
API Request
    ↓
Authentication
    ↓
Validation
    ↓
Interview Logic
    ↓
AI / RAG
    ↓
Output Validation
    ↓
Database
    ↓
Response

### Possible Follow-up Questions

- What happens if validation fails?
- What if the AI API fails?
- How do you prevent duplicate submissions?

---

## Q2. Explain the complete RAG pipeline.

### Answer

RAG generally has two stages: indexing and retrieval.

### Explanation

Indexing:

Documents
    ↓
Text Extraction
    ↓
Chunking
    ↓
Embeddings
    ↓
Vector Database

Query:

User Query
    ↓
Query Embedding
    ↓
Similarity Search
    ↓
Top-K Chunks
    ↓
Prompt + Context
    ↓
LLM
    ↓
Response

### Possible Follow-up Questions

- Why chunk documents?
- What are embeddings?
- What is Top-K?
- What happens if retrieval is wrong?

---

## Q3. Why use RAG instead of relying only on the LLM?

### Answer

An LLM may not contain private, application-specific, or updated
information. RAG allows Aarambh to retrieve relevant information
from its own knowledge source and provide it to the model.

### Example

A job description can be retrieved during candidate evaluation
instead of relying on the LLM's general knowledge.

### Possible Follow-up Questions

- Can RAG eliminate hallucination?
- How do you update the knowledge base?
- What if no document is found?

---

## Q4. What are embeddings and why are they required?

### Answer

Embeddings are numerical vector representations of text that
capture semantic meaning. They allow RAG systems to compare
queries and documents based on meaning.

### Example

"What skills are needed for Java?"

and

"Which Java abilities are required?"

can have similar embeddings.

### Possible Follow-up Questions

- Which embedding model did you use?
- What is vector dimension?
- How are embeddings stored?

---

## Q5. What is a vector database?

### Answer

A vector database stores embeddings and allows efficient
similarity searches over those vectors.

### Explanation

Document
    ↓
Embedding
    ↓
Vector Database

Query
    ↓
Embedding
    ↓
Vector Search
    ↓
Relevant Documents

### Possible Follow-up Questions

- Which vector database did you use?
- What is vector indexing?
- What similarity metric is used?

---

## Q6. Explain cosine similarity.

### Answer

Cosine similarity measures how similar two vectors are based
on the angle between them.

### Formula

cosine_similarity(A,B)
=
(A · B) / (||A|| × ||B||)

### Explanation

It is commonly used to compare text embeddings.

### Possible Follow-up Questions

- Why cosine similarity?
- What is Euclidean distance?
- How are results ranked?

---

## Q7. What is chunking?

### Answer

Chunking is dividing a large document into smaller pieces
before creating embeddings.

### Explanation

Large Document
    ↓
Chunk 1
Chunk 2
Chunk 3
Chunk 4

Smaller chunks make retrieval more precise.

### Possible Follow-up Questions

- What chunk size did you use?
- Why?
- What happens if chunks are too small?

---

## Q8. What is chunk overlap?

### Answer

Chunk overlap means repeating some content between consecutive
chunks so that context is not lost at chunk boundaries.

### Example

Chunk 1:
A B C D E

Chunk 2:
D E F G H

D and E overlap.

### Possible Follow-up Questions

- What happens without overlap?
- How much overlap should be used?
- Can too much overlap cause problems?

---

## Q9. What is Top-K retrieval?

### Answer

Top-K retrieval means selecting the K highest-ranked results
from the retrieval process.

### Example

K = 5

The system retrieves the five most relevant chunks.

### Explanation

Too small a K may miss information.

Too large a K may add irrelevant context and increase token
usage.

### Possible Follow-up Questions

- How do you choose K?
- What happens if K is too large?

---

## Q10. What happens when RAG retrieves irrelevant documents?

### Answer

The LLM may receive incorrect context and produce an irrelevant
or incorrect response.

### Explanation

Possible improvements include:

- Better chunking
- Better embeddings
- Metadata filtering
- Query rewriting
- Re-ranking
- Hybrid search
- Better Top-K selection

### Possible Follow-up Questions

- What is re-ranking?
- What is hybrid search?
- How do you measure retrieval quality?

---

## Q11. What is re-ranking?

### Answer

Re-ranking is a second-stage process that takes initially
retrieved documents and ranks them again based on relevance.

### Explanation

Query
    ↓
Initial Retrieval
    ↓
Top-N
    ↓
Re-ranker
    ↓
Top-K
    ↓
LLM

### Possible Follow-up Questions

- Why use two retrieval stages?
- Does re-ranking increase latency?
- What is a cross-encoder?

---

## Q12. What is hybrid search?

### Answer

Hybrid search combines keyword search and semantic vector
search.

### Explanation

Keyword search is useful for exact terms.

Vector search is useful for semantic meaning.

Combining both can improve retrieval quality.

### Example

"Java 17" benefits from exact keyword matching, while a natural
question about Java skills can benefit from semantic search.

### Possible Follow-up Questions

- What is BM25?
- How are search scores combined?
- Why not use only vector search?

---

## Q13. How do you reduce hallucinations?

### Answer

I would use trusted context, RAG, clear system instructions,
structured outputs, validation, and instructions not to invent
information.

### Explanation

RAG reduces hallucinations but cannot completely eliminate them.

### Example

The model can be instructed:

"Use only the provided information. If the information is not
available, explicitly state that."

### Possible Follow-up Questions

- Can RAG eliminate hallucinations?
- How do you detect hallucinations?
- What happens when retrieval fails?

---

## Q14. How would you structure an interview evaluation prompt?

### Answer

I would clearly define the AI's role, provide the question,
candidate answer, evaluation criteria, and expected output
format.

### Example

You are a technical interviewer.

Evaluate the answer based on:

1. Technical correctness
2. Conceptual understanding
3. Completeness

Return:

{
    "score": 0-10,
    "strengths": [],
    "missing_points": [],
    "feedback": ""
}

Do not invent information.

### Possible Follow-up Questions

- Why structured output?
- How do you validate the JSON?
- What if the output is malformed?

---

## Q15. Why is structured output important?

### Answer

Structured output makes AI responses easier to parse, validate,
store, and display.

### Example

Instead of:

"The candidate performed well."

we can use:

{
    "score": 8,
    "correctness": 9,
    "completeness": 7,
    "feedback": "Good answer."
}

### Possible Follow-up Questions

- How do you validate structured output?
- What if the model returns invalid JSON?

---

## Q16. How would you make AI evaluation consistent?

### Answer

I would use a fixed evaluation rubric, standardized prompts,
controlled model parameters, consistent context, structured
outputs, and benchmark testing.

### Example

Technical Correctness     40%
Conceptual Understanding  30%
Completeness              20%
Communication             10%

### Possible Follow-up Questions

- Can two identical answers get different scores?
- How do you benchmark the model?
- How do you compare AI scores with human scores?

---

## Q17. How would you evaluate an AI-generated candidate score?

### Answer

I would create a benchmark dataset containing questions,
candidate answers, and expert-generated scores. I would compare
the AI's evaluation against the human evaluation.

### Explanation

The evaluation should measure:

- Correctness
- Consistency
- Relevance
- Completeness
- Agreement with human experts

### Possible Follow-up Questions

- What metrics would you use?
- What if AI and human scores differ?
- How would you improve the model?

---

## Q18. What is temperature in an LLM?

### Answer

Temperature controls the randomness of generated responses.

Lower temperature generally produces more deterministic output,
while higher temperature produces more variation.

### Explanation

For candidate evaluation, consistency is generally more important
than creativity.

### Possible Follow-up Questions

- Does temperature affect model intelligence?
- What happens at temperature 0?
- What other generation parameters exist?

---

## Q19. What happens if the AI API fails?

### Answer

The backend should handle the failure using timeout handling,
retries, exponential backoff, logging, and controlled error
responses.

### Explanation

An external AI service should not be treated as guaranteed to
always work.

### Example

Request
    ↓
AI API
    ↓
Failure
    ↓
Retry
    ↓
Success

If retries fail, return a controlled error or queue the request.

### Possible Follow-up Questions

- What is exponential backoff?
- How many retries?
- How would you monitor failures?

---

## Q20. What is caching and where can Aarambh use it?

### Answer

Caching temporarily stores frequently used information so it can
be retrieved faster.

### Example

Frequently accessed interview configuration or static data can
potentially be cached.

### Benefits

- Lower latency
- Fewer database queries
- Lower API usage
- Better scalability

### Possible Follow-up Questions

- What is cache invalidation?
- What should not be cached?
- Which caching technology could be used?

---

## Q21. What is rate limiting?

### Answer

Rate limiting restricts how many requests a user or client can
make during a certain time period.

### Example

100 requests per minute per user.

### Explanation

It protects the system against abuse, excessive traffic, and
unexpected AI API costs.

### Possible Follow-up Questions

- Where should rate limiting happen?
- What happens when the limit is reached?
- How does rate limiting improve security?

---

## Q22. How would you secure Aarambh?

### Answer

I would implement authentication, authorization, secure password
hashing, input validation, HTTPS, protected API keys, rate
limiting, database access controls, and secure logging.

### Explanation

Security must be applied at multiple layers rather than only
at login.

### Possible Follow-up Questions

- What is SQL injection?
- What is prompt injection?
- How do you protect API keys?
- How do you protect candidate data?

---

## Q23. What is SQL injection?

### Answer

SQL injection occurs when malicious input manipulates an
application's SQL query.

### Explanation

Unsafe SQL concatenation can allow attackers to modify the
intended query.

### Prevention

Use:

- Parameterized queries
- Prepared statements
- ORM protections
- Input validation

### Possible Follow-up Questions

- What is a prepared statement?
- Can frontend validation prevent SQL injection?
- Give an example.

---

## Q24. How would you test Aarambh?

### Answer

I would use unit testing, integration testing, API testing,
security testing, and AI-specific evaluation.

### Explanation

Unit tests:
- Validation
- Business logic
- Utility functions

Integration tests:
- Frontend → Backend → AI → Database

AI tests:
- Correct answers
- Incorrect answers
- Partial answers
- Irrelevant answers
- Empty answers
- Adversarial inputs

### Possible Follow-up Questions

- How do you test RAG?
- How do you test an LLM?
- What is integration testing?

---

## Q25. What would you improve in Aarambh?

### Answer

I would improve AI evaluation accuracy, RAG retrieval quality,
security, scalability, monitoring, latency, and structured
evaluation.

### Explanation

Possible improvements include:

- Better retrieval evaluation
- Better prompt engineering
- Human-vs-AI benchmarking
- Better error handling
- Caching
- Asynchronous processing
- Improved authentication
- Monitoring
- Candidate analytics

### Possible Follow-up Questions

- Which improvement would you implement first?
- What is currently the biggest limitation?
- How would you scale the system?