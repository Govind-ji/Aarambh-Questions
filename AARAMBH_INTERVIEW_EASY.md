# AARAMBH AI — TECHNICAL INTERVIEW QUESTIONS
# EASY SET — 25 QUESTIONS

---

## Q1. What is Aarambh?

### Answer

Aarambh is an AI-based interview system designed to automate
different parts of the interview process, interact with
candidates, process their responses, and generate structured
evaluation.

### Explanation

The main goal is to reduce manual effort during the initial
interview process and provide a more consistent evaluation.

### Example

Candidate
    ↓
Interview Question
    ↓
Candidate Answer
    ↓
AI Processing
    ↓
Evaluation
    ↓
Result

### Possible Follow-up Questions

- What problem does Aarambh solve?
- What was your role?
- What technologies did you use?
- Explain the architecture.

---

## Q2. What problem does Aarambh solve?

### Answer

Aarambh attempts to automate the initial interview and candidate
evaluation process, reducing manual effort and improving
consistency.

### Explanation

In a traditional interview, an interviewer has to ask questions,
analyze answers, assign scores, and provide feedback manually.

Aarambh automates parts of this workflow using AI.

### Example

A company receiving hundreds of applications can use Aarambh
for AI-assisted initial screening.

### Possible Follow-up Questions

- Why is AI required?
- Why not use a rule-based system?
- Can AI completely replace interviewers?

---

## Q3. Why did you choose Aarambh as a project?

### Answer

We chose Aarambh because interviewing contains repetitive tasks
that can potentially be automated. It also allowed us to combine
software engineering with Artificial Intelligence and NLP to
solve a practical problem.

### Explanation

The project involves multiple technical areas such as AI,
backend development, APIs, databases, and natural-language
processing.

### Example

Instead of building only a basic CRUD application, we attempted
to solve a real-world problem using AI.

### Possible Follow-up Questions

- What makes Aarambh different?
- What did you learn?
- What was the biggest challenge?

---

## Q4. What was your role in Aarambh?

### Answer

My primary contribution was on the AI and technical side of the
project. I worked on the logic required for processing
interview-related information, integrating AI functionality,
and understanding how candidate responses could be evaluated.

### Explanation

I should be able to explain the exact modules and code that I
personally worked on.

### Example

For my module, I should be able to explain:

- Input
- Processing
- AI integration
- Output
- Testing
- Integration with other modules

### Possible Follow-up Questions

- Which files did you work on?
- Show me your code.
- What was your biggest technical challenge?

---

## Q5. Explain the high-level architecture of Aarambh.

### Answer

Aarambh consists of a frontend, backend/API layer, AI processing
layer, and database. If RAG is used, a retrieval and vector
storage layer is also involved.

### Explanation

Basic architecture:

Frontend
    ↓
Backend
    ↓
AI / LLM
    ↓
Evaluation
    ↓
Database

With RAG:

Backend
    ↓
Retrieval
    ↓
Vector Database
    ↓
Context
    ↓
LLM
    ↓
Evaluation

### Possible Follow-up Questions

- Where does RAG fit?
- Where is authentication?
- Where is the database accessed?

---

## Q6. Why did you use AI in Aarambh?

### Answer

Candidate responses are open-ended and can express the same
concept using different words. AI can understand semantic
meaning better than simple keyword matching or fixed rules.

### Example

Two candidates may explain polymorphism differently while both
being correct.

### Possible Follow-up Questions

- Why not use rules?
- What are the limitations of AI?
- How do you evaluate AI output?

---

## Q7. What is Artificial Intelligence?

### Answer

Artificial Intelligence is a field of computer science focused
on creating systems capable of performing tasks that normally
require human intelligence.

### Explanation

Examples include:

- Language understanding
- Pattern recognition
- Prediction
- Decision-making
- Content generation

### Possible Follow-up Questions

- What is Machine Learning?
- What is Deep Learning?
- What is Generative AI?

---

## Q8. What is Machine Learning?

### Answer

Machine Learning is a subset of AI where systems learn patterns
from data instead of being explicitly programmed with every
possible rule.

### Explanation

Traditional programming:

Input + Rules → Output

Machine Learning:

Data → Model → Prediction

### Possible Follow-up Questions

- What is supervised learning?
- What is unsupervised learning?
- What is deep learning?

---

## Q9. What is NLP?

### Answer

NLP stands for Natural Language Processing. It enables computers
to understand, process, analyze, and generate human language.

### Explanation

Aarambh deals with interview questions and candidate responses,
which are natural-language data.

### Example

Question + Candidate Answer
    ↓
NLP / LLM Processing
    ↓
Evaluation

### Possible Follow-up Questions

- What is tokenization?
- What is semantic similarity?
- What are embeddings?

---

## Q10. What is an LLM?

### Answer

LLM stands for Large Language Model. It is trained on a large
amount of text data to understand and generate natural language.

### Explanation

LLMs can perform tasks such as:

- Question answering
- Text generation
- Summarization
- Classification
- Information extraction

### Possible Follow-up Questions

- Which LLM did you use?
- Why did you choose it?
- What is temperature?
- What is hallucination?

---

## Q11. Why use an LLM instead of a rule-based system?

### Answer

Rule-based systems work well for predictable inputs, but
interview answers are open-ended. An LLM can understand
different ways of expressing the same concept.

### Example

A candidate can explain polymorphism without using the exact
keywords expected by a rule-based system.

### Possible Follow-up Questions

- What are the disadvantages of LLMs?
- How do you control LLM output?
- How do you reduce hallucinations?

---

## Q12. What is an API?

### Answer

An API, or Application Programming Interface, provides a way
for different software components to communicate.

### Example

Frontend
    ↓
API Request
    ↓
Backend
    ↓
AI Service
    ↓
API Response
    ↓
Frontend

### Possible Follow-up Questions

- What is REST?
- What is HTTP?
- What is JSON?

---

## Q13. What is REST API?

### Answer

REST is an architectural style commonly used to build web APIs
using HTTP methods.

### Explanation

GET → Retrieve
POST → Create
PUT → Update
PATCH → Partial Update
DELETE → Delete

### Possible Follow-up Questions

- PUT vs PATCH?
- What are HTTP status codes?
- What is idempotency?

---

## Q14. What is JSON?

### Answer

JSON stands for JavaScript Object Notation. It is commonly used
to exchange structured data between applications.

### Example

{
    "candidateId": 101,
    "question": "What is inheritance?",
    "answer": "Inheritance allows..."
}

### Possible Follow-up Questions

- JSON vs XML?
- What is serialization?
- How is JSON parsed?

---

## Q15. Why does Aarambh need a database?

### Answer

A database provides persistent storage for candidates,
interviews, questions, answers, scores, and evaluation results.

### Example

Candidate
    ↓
Interview
    ↓
Answers
    ↓
Evaluation
    ↓
Database

### Possible Follow-up Questions

- Which database did you use?
- Why?
- How did you design the tables?

---

## Q16. What is a primary key?

### Answer

A primary key uniquely identifies each record in a database
table.

### Example

candidate_id can uniquely identify a candidate.

### Possible Follow-up Questions

- What is a foreign key?
- Can a primary key contain NULL?
- What is a composite key?

---

## Q17. What is a foreign key?

### Answer

A foreign key is a column that references a key in another
table and establishes a relationship between tables.

### Example

Candidate:
candidate_id

Interview:
interview_id
candidate_id

### Possible Follow-up Questions

- What is referential integrity?
- What are joins?
- What is normalization?

---

## Q18. What is authentication?

### Answer

Authentication is the process of verifying the identity of
a user.

### Example

Email + Password
    ↓
Authentication
    ↓
User Identity

### Possible Follow-up Questions

- What is authorization?
- What is JWT?
- How are passwords stored?

---

## Q19. What is authorization?

### Answer

Authorization determines what an authenticated user is allowed
to access or perform.

### Example

Candidate → Own interview

Recruiter → Candidate results

Admin → System management

### Possible Follow-up Questions

- What is RBAC?
- How would you implement role-based access?

---

## Q20. What is JWT?

### Answer

JWT stands for JSON Web Token. It is commonly used for
stateless authentication.

### Explanation

Login
    ↓
Credentials Verified
    ↓
JWT Generated
    ↓
Client Sends Token
    ↓
Server Verifies Token

### Possible Follow-up Questions

- What is inside a JWT?
- Is JWT encrypted?
- What is a refresh token?

---

## Q21. What is hallucination in AI?

### Answer

Hallucination occurs when an AI model generates incorrect,
unsupported, or fabricated information as if it were factual.

### Example

If a candidate's resume does not mention AWS but the AI claims
the candidate has AWS experience, that is hallucination.

### Possible Follow-up Questions

- How do you reduce hallucination?
- Can RAG eliminate hallucinations?
- How can hallucinations be detected?

---

## Q22. What is prompt engineering?

### Answer

Prompt engineering is designing instructions, context, examples,
and output requirements to obtain more reliable and consistent
LLM responses.

### Example

"Evaluate the candidate only using the supplied question,
answer, and evaluation criteria. Do not invent information."

### Possible Follow-up Questions

- What is zero-shot prompting?
- What is few-shot prompting?
- How do you test prompts?

---

## Q23. What is RAG?

### Answer

RAG stands for Retrieval-Augmented Generation. It retrieves
relevant information from an external knowledge source and
provides it to an LLM as context before generating a response.

### Explanation

Without RAG:

Query → LLM → Answer

With RAG:

Query → Retrieval → Context → LLM → Answer

### Possible Follow-up Questions

- Why use RAG?
- What are embeddings?
- What is a vector database?
- Explain the RAG pipeline.

---

## Q24. What are embeddings?

### Answer

Embeddings are numerical vector representations of information,
especially text, that capture semantic meaning.

### Example

Text
    ↓
Embedding Model
    ↓
Vector

Similar meanings generally produce vectors that are close in
vector space.

### Possible Follow-up Questions

- Why are embeddings needed?
- What is cosine similarity?
- Where are embeddings stored?

---

## Q25. What was the biggest technical challenge in Aarambh?

### Answer

One of the biggest challenges in an AI-based application is
making AI output reliable and consistent enough to integrate
into a software workflow.

### Explanation

Unlike traditional deterministic code, LLM output can vary.
Therefore, prompt design, structured output, validation, error
handling, and testing are important.

### Possible Follow-up Questions

- How did you solve it?
- What limitation remains?
- What would you improve?