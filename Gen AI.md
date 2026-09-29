# 🤖 Generative AI — Complete Notes

### English + Hindi | Assessment + Interview

---

# 1. What is Generative AI? ⭐⭐⭐⭐⭐

### English

**Generative AI is a type of Artificial Intelligence that can create new content such as text, images, audio, video, and code by learning patterns from large amounts of data.**

### Hindi

**Generative AI, Artificial Intelligence ka ek type hai jo large amount of data se patterns learn karke naya content generate kar sakta hai**, jaise:

-  Text 
-  Images 
-  Audio 
-  Video 
-  Code 

### Example

Agar tum ChatGPT ko bolo:

> "Explain DBMS in simple words."

Model tumhare prompt ke basis par **new text response generate** karta hai.

### Interview Answer

> **Generative AI is a type of AI that learns patterns from data and uses those learned patterns to generate new content such as text, images, audio, video, and code.**

---

# 2. Why is it called "Generative" AI?

### English

It is called **Generative** because the system generates new output rather than simply classifying or predicting an existing category.

### Hindi

Isko **Generative** isliye kaha jata hai kyunki ye sirf existing data ko classify nahi karta, balki **naya content generate** karta hai.

### Example

Traditional AI:

> "Is image mein cat hai ya dog?"

Output:

> Cat

Generative AI:

> "Generate an image of a cat sitting in a garden."

Output:

> New image

### Interview Question

**Q: Why is Generative AI called generative?**

**Answer:**

> Because it can generate new content based on patterns learned during training instead of only classifying or predicting existing data.

---

# 3. Traditional AI vs Generative AI ⭐⭐⭐⭐⭐

| Traditional AI            | Generative AI                        |
| ------------------------- | ------------------------------------ |
| Classification/prediction | Content generation                   |
| Detects patterns          | Learns patterns and generates output |
| Spam detection            | Email generation                     |
| Fraud detection           | Report generation                    |
| Face recognition          | Image generation                     |
| Recommendation            | Text/code generation                 |

### Interview Question

**Q: What is the difference between traditional AI and Generative AI?**

### Answer

> Traditional AI is commonly used for tasks such as classification, prediction, and decision support, whereas Generative AI focuses on creating new content such as text, images, code, audio, or video.

### Follow-up

**Q: Give one real-world example.**

**Answer:**

> A fraud detection system can classify a transaction as fraudulent or legitimate, while a Generative AI system can generate a customer email or report.

---

# 4. Is Generative AI the same as AI? ⭐⭐⭐⭐⭐

**No.**

AI is a broad field.

Generative AI is a **subset/application of AI** focused on generating content.

```
```

```
Artificial Intelligence
        │
        ├── Traditional AI
        │
        └── Generative AI
              │
              ├── Text
              ├── Image
              ├── Audio
              ├── Video
              └── Code
```

### Hindi

AI ek **broad field** hai, jabki Generative AI AI ka ek part hai jo **new content create** karta hai.

### Follow-up

**Q: Is every AI system a Generative AI system?**

**Answer:**

> No. Many AI systems perform classification, prediction, recommendation, or detection without generating new content.

---

# 5. How does Generative AI work? ⭐⭐⭐⭐⭐

High-level understanding bahut important hai.

```
```

```
Large Training Data
        ↓
Model Training
        ↓
Model learns patterns
        ↓
User gives Prompt
        ↓
Model processes input
        ↓
Model generates output
```

### Hindi

1.  Model ko large amount of data diya jata hai. 
2.  Training ke through model data ke patterns learn karta hai. 
3.  User prompt deta hai. 
4.  Model prompt ko process karta hai. 
5.  Model learned patterns ke basis par output generate karta hai. 

### Important

Model simply training data ko copy-paste nahi karta. Generative models learned representations/patterns ka use karke output generate karte hain.

---

# 6. Training vs Inference ⭐⭐⭐⭐

Ye interview mein follow-up ban sakta hai.

### Training

Model **data se learn** karta hai.

```
```

```
Data → Training → Model
```

### Inference

Trained model ko input/prompt diya jata hai aur output generate hota hai.

```
```

```
Prompt → Trained Model → Output
```

### Interview Question

**Q: What is the difference between training and inference?**

### Answer

> Training is the process of learning patterns or parameters from data. Inference is the process of using the trained model to generate predictions or outputs for new inputs.

---

# 7. What types of content can Generative AI create? ⭐⭐⭐⭐

### Text

Chatbots, emails, summaries, reports

### Images

AI-generated artwork, product images

### Audio

Speech, music, sound

### Video

AI-generated videos

### Code

Code generation, explanation, documentation

### Interview Question

**Q: Give five applications of Generative AI.**

Answer:

> Text generation, image generation, code generation, audio generation, and video generation.

---

# 8. Generative AI and LLM ⭐⭐⭐⭐⭐

This is **very important**.

### LLM

**LLM = Large Language Model**

LLM language-related tasks ke liye designed hota hai.

Examples of tasks:

-  Text generation 
-  Summarization 
-  Translation 
-  Question answering 
-  Code generation 

### Relationship

```
```

```
AI
 ↓
Generative AI
 ↓
Language-based Generative Models
 ↓
LLMs
```

### Important

**Every LLM is not necessarily the whole of Generative AI.**

Generative AI also includes models for:

-  Images 
-  Audio 
-  Video 

### Interview Question

**Q: What is the relationship between Generative AI and LLM?**

### Answer

> Generative AI is a broad category of AI systems that generate content. An LLM is a type of generative model specialized in processing and generating language.

---

# 9. Generative AI and Machine Learning ⭐⭐⭐⭐⭐

### Machine Learning

Machine Learning allows systems to learn patterns from data.

### Generative AI

Generative AI uses machine-learning/deep-learning techniques to generate new content.

Example:

**ML:**

> Predict whether a customer will leave.

**GenAI:**

> Generate a personalized message for that customer.

### Interview Question

**Q: Is Generative AI a form of Machine Learning?**

### Answer

> Generative AI is built using machine-learning and deep-learning techniques, although the specific architecture and training methods can vary.

---

# 10. Deep Learning and Generative AI ⭐⭐⭐⭐

Modern Generative AI systems commonly use **deep neural networks**.

Deep learning allows models to learn complex patterns from large datasets.

Examples of model families/architectures include:

-  Transformers 
-  Diffusion models 
-  GANs 
-  Variational Autoencoders 

For your Capgemini preparation, **basic awareness is enough** unless the job description specifically asks for deep ML knowledge.

---

# 11. What is a Generative AI Model? ⭐⭐⭐⭐

A Generative AI model is a model trained to generate new data/content.

Examples:

```
```

```
Text → Language model
Image → Image generation model
Audio → Audio generation model
```

### Interview Follow-up

**Q: What determines the quality of generated output?**

Possible factors:

-  Training data quality 
-  Model architecture 
-  Prompt quality 
-  Context provided 
-  Model capabilities 
-  Parameters/settings 
-  Retrieval/grounding when used 

---

# 12. What is a Prompt? ⭐⭐⭐⭐⭐

A **prompt** is the input/instruction given to an AI model.

Example:

> "Explain DBMS in simple English with an example."

Here, the complete instruction is the **prompt**.

### Hindi

Prompt basically woh instruction/input hai jo hum AI model ko dete hain.

---

# 13. Prompt Engineering ⭐⭐⭐⭐⭐

Prompt Engineering means **designing effective prompts to get useful and desired outputs from an AI model.**

### Poor Prompt

> Explain AI.

### Better Prompt

> Explain Generative AI to a beginner in simple English using two real-world examples.

Better prompt contains:

-  Task 
-  Context 
-  Audience 
-  Constraints 
-  Expected format 

### Interview Question

**Q: What is Prompt Engineering?**

### Answer

> Prompt engineering is the process of designing and refining instructions given to an AI model to obtain more relevant, accurate, and useful outputs.

---

# 14. Zero-shot Prompting ⭐⭐⭐⭐

No example is provided.

```
```

```
Translate this sentence into Hindi:
"I love programming."
```

Model directly performs the task.

### Hindi

Model ko koi example nahi diya gaya.

---

# 15. Few-shot Prompting ⭐⭐⭐⭐

Model ko examples diye jate hain.

```
```

```
English: Good morning
Hindi: सुप्रभात

English: Thank you
Hindi: धन्यवाद

English: Good night
Hindi:
```

Model examples ke pattern ko follow karta hai.

### Interview Question

**Q: Zero-shot and few-shot prompting mein difference?**

### Answer

> Zero-shot prompting provides only the task without examples, while few-shot prompting provides one or more examples to guide the model's expected behavior or output format.

---

# 16. Temperature ⭐⭐⭐⭐⭐

Temperature output ki **randomness/variation** ko influence karta hai.

### Lower Temperature

→ More predictable/consistent output

### Higher Temperature

→ More varied output

```
```

```
Low Temperature
       ↓
More predictable

High Temperature
       ↓
More variation
```

### Interview Question

**Q: When would you use lower temperature?**

> When consistent and predictable responses are preferred, such as structured or factual-style tasks.

### Follow-up

**Q: Does higher temperature guarantee a better answer?**

**No.**

It changes the degree of variation; it does not guarantee correctness or quality.

---

# 17. Hallucination ⭐⭐⭐⭐⭐

**Very important.**

### Definition

Hallucination occurs when an AI model generates information that is **incorrect, fabricated, or unsupported**, sometimes with high confidence.

### Example

User:

> Give me the official source for a fictional research paper.

AI:

> Generates a fake paper/citation.

That's hallucination.

### Hindi

Jab AI **galat ya fabricated information ko confidently generate** karta hai, use hallucination kehte hain.

---

# 18. How can hallucination be reduced? ⭐⭐⭐⭐⭐

Methods:

-  Better prompts 
-  Provide relevant context 
-  RAG 
-  Grounding 
-  Retrieval from trusted sources 
-  Fact verification 
-  Human review 
-  Appropriate model/system design 

### Interview Question

**Q: Can hallucination be completely eliminated?**

Safe answer:

> It can be reduced significantly through techniques such as grounding, retrieval, better prompting, validation, and human oversight, but it should not be assumed that hallucinations can always be completely eliminated.

---

# 19. RAG and Generative AI ⭐⭐⭐⭐⭐

**RAG = Retrieval-Augmented Generation**

RAG allows an AI system to retrieve relevant information from an external knowledge source and use that information while generating a response.

### Basic flow

```
```

```
User Question
      ↓
Retrieve relevant information
      ↓
Relevant Context
      ↓
LLM
      ↓
Generated Answer
```

### Example

Company ke paas 500 internal documents hain.

Employee asks:

> "What is our leave policy?"

RAG system:

```
```

```
Question
   ↓
Search company documents
   ↓
Find relevant leave-policy section
   ↓
Give context to model
   ↓
Generate answer
```

---

# 20. Embeddings ⭐⭐⭐⭐⭐

Embedding kisi data—commonly text—ka **numerical/vector representation** hota hai.

Example:

```
```

```
"Java is a programming language"
             ↓
         Embedding
             ↓
   [0.12, -0.32, 0.71, ...]
```

Embeddings semantic similarity/search ke liye useful hain.

### Hindi

Text ko numbers ke vector mein represent karna, jisse system meaning/similarity ke basis par comparison/search kar sake.

---

# 21. Vector Database ⭐⭐⭐⭐⭐

Vector database embeddings ko store aur efficiently search karne ke liye use kiya ja sakta hai.

```
```

```
Document
   ↓
Embedding
   ↓
Vector Database
   ↓
Similarity Search
```

RAG systems mein vector databases commonly use hote hain.

---

# 22. Grounding ⭐⭐⭐⭐⭐

Grounding ka matlab AI ke response ko **relevant, reliable external/contextual information** se anchor karna.

### Example

Without grounding:

> Model apni learned knowledge se answer generate karta hai.

With grounding:

> Model ko trusted company documents provide kiye jate hain, aur answer un documents ke context par based hota hai.

### Interview Question

**Q: Why is grounding useful?**

> Grounding can help reduce unsupported responses by providing the model with relevant external context.

---

# 23. RAG vs Fine-tuning ⭐⭐⭐⭐⭐

| RAG                                         | Fine-tuning                                         |
| ------------------------------------------- | --------------------------------------------------- |
| External information retrieve karta hai     | Model ko additional training se adapt karta hai     |
| Knowledge source easily update ho sakta hai | Training/update process required                    |
| Enterprise documents ke liye useful         | Specialized behavior/task adaptation ke liye useful |
| Retrieval + generation                      | Model adaptation                                    |

### Interview Question

**Q: If company policy changes frequently, would RAG often be useful?**

Yes, because the external knowledge source can be updated without necessarily retraining the underlying model for every policy change.

---

# 24. Multimodal Generative AI ⭐⭐⭐⭐

**Multimodal AI** multiple types of information work kar sakta hai.

For example:

```
```

```
Text
 ↓
AI Model
 ↑
Image
```

A system may accept:

-  Text 
-  Image 
-  Audio 
-  Video 

and potentially generate different modalities depending on the system.

### Interview Question

**Q: What is multimodal AI?**

> AI that can work with multiple modalities such as text, images, audio, or video.

---

# 25. Advantages of Generative AI ⭐⭐⭐⭐

### English

-  Automation 
-  Faster content creation 
-  Coding assistance 
-  Summarization 
-  Personalization 
-  Customer support 
-  Productivity improvement 
-  Creative assistance 

### Hindi

-  Repetitive work automate karna 
-  Content quickly create karna 
-  Coding mein help 
-  Large information summarize karna 
-  Customer support 
-  Productivity improve karna 

---

# 26. Limitations of Generative AI ⭐⭐⭐⭐⭐

Interview mein ye list yaad rakho:

### 1. Hallucination

Incorrect/fabricated output.

### 2. Bias

Training data ke bias ka effect.

### 3. Privacy

Sensitive information ka risk.

### 4. Security

Prompt injection/data leakage jaise risks.

### 5. Reliability

Output always correct nahi hota.

### 6. Context limitations

Large information ko process karne ki limitations ho sakti hain.

### 7. Cost/compute

Large models ko significant computational resources ki zarurat ho sakti hai.

### 8. Human oversight

High-impact applications mein human review important ho sakta hai.

---

# 27. Responsible AI ⭐⭐⭐⭐⭐

Generative AI ko responsibly use karne ke liye important principles:

- **Fairness** 
- **Transparency** 
- **Privacy** 
- **Security** 
- **Accountability** 
- **Safety** 
- **Human oversight** 

### Interview Question

**Q: Why is Responsible AI important?**

> Because AI systems can affect people and organizations, and they may introduce risks such as bias, privacy violations, incorrect outputs, and security problems. Responsible AI practices help manage these risks.

---

# 🔥 Top Interview Questions + Follow-ups

Ab ye section **especially interview ke liye** important hai.

---

### Q1. What is Generative AI?

**Answer:**

> Generative AI is a type of AI that learns patterns from data and generates new content such as text, images, audio, video, or code.

**Follow-up:**

**How is it different from traditional AI?**

→ Traditional AI often focuses on prediction/classification, while Generative AI focuses on creating new content.

---

### Q2. Give a real-world example.

**Answer:**

> Chatbots that generate text responses, AI coding assistants, image generation systems, and tools that summarize documents are examples of Generative AI applications.

**Follow-up:**

**Is ChatGPT Generative AI?**

→ Yes, it is a Generative AI application based on language models.

---

### Q3. Is Generative AI the same as LLM?

**Answer:**

> No. Generative AI is a broader category. LLMs are models specialized in language-related tasks and are one important type of Generative AI.

**Follow-up:**

**Can Generative AI generate images?**

→ Yes.

**Follow-up:**

**Can an LLM generate images?**

→ It depends on the specific system/model; language-only models and multimodal/generative systems have different capabilities.

---

### Q4. How does Generative AI work?

**Answer:**

> During training, the model learns patterns from data. During inference, it receives an input or prompt and generates output based on what it has learned and the context available to it.

**Follow-up:**

**What is inference?**

→ Using a trained model to produce output for new input.

---

### Q5. What is hallucination?

**Answer:**

> Hallucination is when an AI model generates incorrect, fabricated, or unsupported information.

**Follow-up:**

**How can we reduce it?**

→ RAG, grounding, reliable retrieval, better prompting, validation, and human review.

---

### Q6. What is RAG?

**Answer:**

> RAG stands for Retrieval-Augmented Generation. It retrieves relevant external information and provides it as context to a generative model before generating the answer.

**Follow-up:**

**Why use RAG?**

→ To provide relevant external knowledge and help ground responses.

**Follow-up:**

**What is used to store embeddings?**

→ A vector database can be used.

---

### Q7. What is Prompt Engineering?

**Answer:**

> Prompt engineering is the process of designing effective instructions for an AI model to obtain more relevant and useful outputs.

**Follow-up:**

**What makes a good prompt?**

→ Clear task, context, constraints, expected format, and examples when useful.

---

### Q8. What is temperature?

**Answer:**

> Temperature is a generation setting that influences the degree of randomness or variation in model outputs.

**Follow-up:**

**High temperature?**

→ More variation.

**Follow-up:**

**Low temperature?**

→ More predictable output.

---

### Q9. What is an embedding?

**Answer:**

> An embedding is a numerical vector representation of data, commonly text, that can capture useful semantic relationships and enable similarity-based search.

**Follow-up:**

**Where is it used?**

→ Semantic search, recommendation systems, and RAG pipelines.

---

### Q10. RAG vs Fine-tuning?

**Answer:**

> RAG retrieves external information at query time, while fine-tuning adapts the model through additional training. RAG is often useful when external knowledge changes frequently, while fine-tuning can be useful for specialized behavior or task adaptation.

**Follow-up:**

**Company policies change every month. What can help?**

→ RAG can often be a suitable approach because the external knowledge base can be updated.

---

# 🧠 Capgemini Assessment — Most Important MCQs

### 1. Generative AI primarily focuses on:

A. Only classification

B. Creating new content

C. Only database management

D. Only networking

✅ **Answer: B**

---

### 2. Which is NOT typically a Generative AI output?

A. Text

B. Image

C. Code

D. CPU temperature measurement

✅ **Answer: D**

---

### 3. LLM stands for:

A. Large Learning Machine

B. Large Language Model

C. Language Learning Machine

D. Logical Language Model

✅ **Answer: B**

---

### 4. Which is an example of hallucination?

A. Correct calculation

B. Generating a fabricated citation

C. Searching a database

D. Sorting an array

✅ **Answer: B**

---

### 5. RAG stands for:

A. Retrieval-Augmented Generation

B. Random AI Generation

C. Retrieval AI Gateway

D. Real-time AI Generation

✅ **Answer: A**

---

### 6. What does an embedding represent?

A. Only an image file

B. Numerical representation of data

C. Database password

D. Programming language

✅ **Answer: B**

---

### 7. Which technology is commonly used to search embeddings?

A. Vector database

B. Compiler

C. Operating system

D. HTML

✅ **Answer: A**

---

### 8. Few-shot prompting means:

A. No examples

B. Multiple examples are provided

C. No prompt

D. Model is retrained

✅ **Answer: B**

---

### 9. Higher temperature generally results in:

A. More variation

B. Guaranteed accuracy

C. No output

D. Model retraining

✅ **Answer: A**

---

### 10. Which is a Responsible AI principle?

A. Privacy

B. Ignoring bias

C. Removing human oversight

D. Hiding model limitations

✅ **Answer: A**