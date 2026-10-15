# Capgemini AI Literacy Notes

## Topic 11: Tokenization --- Basic to Advanced

**Study format:** Hinglish explanations · Interview answers ·
Scenario-based MCQs · Quick revision

------------------------------------------------------------------------

## How to Use These Notes

1.  Understand the concept in simple language.
2.  Remember the key difference tables.
3.  Attempt the scenario-based MCQs before reading the answers.
4.  Revise the quick-revision section before the assessment.

> The practice questions in these notes are original study questions,
> not verified questions from an actual Capgemini exam.

# Part A --- Tokenization

## 1. What Is Tokenization?

**English definition:** Tokenization is the process of breaking text
into smaller units called tokens so that a language model can process
the text.

**Hindi:** Tokenization mein text ko chhote units, yaani tokens, mein
divide kiya jaata hai. Ye units complete words, word-parts, punctuation,
ya doosre text units ho sakte hain.

### Example

Input text:

`I love AI!`

One possible tokenization:

`I` · `love` · `AI` · `!`

*Illustrative example only: actual token boundaries depend on the
tokenizer and model.*

### Key points

-   One token does **not** always equal one word.
-   A common word may be represented by one token.
-   An uncommon word may be split into multiple tokens.
-   Punctuation, numbers, spaces, language, and tokenizer design can
    affect token count.

**Interview answer:** Tokenization is the process of splitting text into
tokens that a language model can process.

## 2. Why Do LLMs Need Tokenization?

Language models process text through a numerical representation. A
tokenizer splits text into tokens and maps those tokens to numerical
token IDs.

### Simplified pipeline

`Input text → Tokens → Token IDs → Embedding vectors → Model processing`

Example:

-   Input text: `Hello world!`
-   Tokens: `Hello` · `world` · `!`
-   Token IDs: `[ID₁, ID₂, ID₃]` *(illustrative; actual IDs depend on
    the tokenizer vocabulary)*

### Main purposes

1.  Represent text as manageable units.
2.  Help represent common and unfamiliar words.
3.  Provide token sequences for model input and output.
4.  Help measure token usage and manage context-window limits.

## 3. Types of Tokenization

### 3.1 Word-Level Tokenization

Text is split into complete words.

**Example:** `I love AI` → `I` \| `love` \| `AI`

**Limitation:** Handling every possible word can require a very large
vocabulary. New or rare words can be difficult to represent if they are
not in the vocabulary.

### 3.2 Character-Level Tokenization

Text is split into individual characters.

**Example:** `cat` → `c` \| `a` \| `t`

**Advantage:** Unfamiliar words can be represented as sequences of
characters.

**Limitation:** Sequences can become long, and the model must learn
word-level patterns from smaller units.

### 3.3 Subword Tokenization

Words are represented using common subword units. A word can remain one
token or be split into multiple subword tokens.

**Illustrative example:** `unbelievable` → `un` \| `believ` \| `able`

**Advantages:** - Helps represent rare or unfamiliar words. - Can
balance vocabulary size and sequence length. - Is common in modern
language-model tokenization approaches.

**Exam tip:** If a question asks how a model can represent an unfamiliar
word that is not present as a complete vocabulary item, subword
tokenization is often a strong answer.

## 4. Advanced Tokenization Methods

  -----------------------------------------------------------------------
  Method                  Core idea               Remember
  ----------------------- ----------------------- -----------------------
  **BPE (Byte Pair        Repeatedly merges       Think: frequent-pair
  Encoding)**             frequent symbol pairs   merging.
                          during vocabulary       
                          construction.           

  **WordPiece**           Uses learned criteria   Associated with models
                          to select subword       such as BERT.
                          units.                  

  **Unigram Language      Uses a probabilistic    Think: probabilistic
  Model**                 approach over candidate subword selection.
                          subword units.          

  **Byte-level            Uses byte-level units   Can help represent a
  tokenization**          as a basis for          broad range of text.
                          representing text.      
  -----------------------------------------------------------------------

You generally need to understand each method's basic purpose and
difference before studying its mathematics.

## 5. Special Tokens

Some models and formats use special tokens or message markers to
represent structure or control information.

  -----------------------------------------------------------------------
  Type                                Possible purpose
  ----------------------------------- -----------------------------------
  **BOS (Beginning of Sequence)**     Marks the beginning of a sequence
                                      in formats that use it.

  **EOS (End of Sequence)**           Marks the end of a sequence or
                                      generation.

  **Padding token**                   Helps align sequence lengths during
                                      batch processing.

  **UNK (Unknown token)**             Represents an unrecognized unit in
                                      some tokenizers.

  **Role/format markers**             Can indicate message roles,
                                      boundaries, or structured output.
  -----------------------------------------------------------------------

Not every model uses all these tokens. Their exact form and behavior
depend on the tokenizer and model format.

**Scenario example:** A chatbot needs to distinguish system
instructions, user messages, and assistant responses. Message markers or
special tokens can help represent those boundaries.

## 6. Tokenization vs Token IDs vs Embeddings vs Attention

  -----------------------------------------------------------------------
  Concept                             What it does
  ----------------------------------- -----------------------------------
  **Tokenization**                    Splits text into tokens.

  **Token IDs**                       Numerical identifiers assigned to
                                      tokens by a tokenizer's vocabulary.

  **Embeddings**                      Numerical vector representations of
                                      tokens or other inputs.

  **Attention**                       Helps a model process relationships
                                      between tokens in context.
  -----------------------------------------------------------------------

**Memory formula:**

`Text → Tokens → Token IDs → Embedding vectors → Model processing`

This is a simplified conceptual pipeline; implementation details vary by
architecture.

## 7. Token Count, Context Window, and Cost

-   Model input capacity is commonly described in tokens, not simply
    words or characters.
-   Prompts, instructions, conversation history, and supplied documents
    can consume tokens.
-   Depending on the model and API, generated output may also use part
    of the available token budget.
-   Two texts with the same number of words can have different token
    counts.
-   Some APIs charge based on input and output token usage; pricing
    depends on the provider and model.

**Important:** Token count is not the same as word count. "One token =
one word" is an incorrect generalization.

## 8. Tokenization: Scenario-Based MCQs

Choose one answer per question before checking the answer key.

### Q1. Unfamiliar word

A customer-support LLM receives the word "unhappiness," which is not
present as a complete word in its vocabulary. The model still needs to
process it. Which approach can help?

A. Reject the input because the complete word is unknown\
B. Split the word into available subword units\
C. Convert the whole sentence directly into embeddings without
tokenization\
D. Increase temperature

### Q2. Word count vs token count

A developer assumes that a 100-word prompt always uses exactly 100
tokens. Why is this assumption incorrect?

A. Tokens only count punctuation\
B. Every word always maps to two tokens\
C. Token counts depend on the tokenizer, text, language, and word
structure\
D. Token counts are determined only by temperature

### Q3. Long document

An LLM application sends a very long company policy document to the
model, but the end of the document is missing from the processed input.
What is the most relevant concern?

A. The model has too many parameters\
B. Input truncation or context-window limits\
C. The temperature is too low\
D. Embeddings have converted words into characters

### Q4. Vocabulary and rare words

A team wants to keep vocabulary size manageable while still representing
rare words. Which approach is generally suitable?

A. Subword tokenization\
B. Only word-level tokenization\
C. Removing all punctuation\
D. Increasing model temperature

### Q5. Token IDs

A developer sees token IDs such as `[1542, 982, 27]` after preprocessing
a sentence. What do these numbers represent?

A. The model's final answer\
B. Embedding dimensions only\
C. Numerical IDs assigned to tokens by a tokenizer\
D. The number of words in the sentence

### Q6. Message boundaries

A chatbot needs to distinguish message boundaries and mark the end of a
sequence. Which concept is most relevant?

A. Temperature scaling only\
B. Special tokens or message markers\
C. Word frequency alone\
D. Increasing context length

### Q7. Multilingual text

A team processes customer feedback in several languages. Two reviews
have the same number of words but different token counts. What is the
best explanation?

A. One review must be corrupted\
B. All tokenizers use one token per word\
C. Language and tokenizer behavior can change how text is split\
D. The model always counts emojis as sentences

### Q8. Tokenization vs embeddings

An engineer says, "Tokenization and embeddings are the same because both
convert text into numbers." Which correction is best?

A. Tokenization splits text and maps units to IDs; embeddings represent
tokens or inputs as vectors\
B. Embeddings split words, while tokenization generates the final
answer\
C. Both are identical operations in every model\
D. Tokenization is only used during training

## 9. Tokenization MCQ Answer Key

  -----------------------------------------------------------------------
  Question                Answer                  Explanation
  ----------------------- ----------------------- -----------------------
  1                       **B**                   Subword tokenization
                                                  can represent an
                                                  unfamiliar word using
                                                  smaller units in the
                                                  vocabulary.

  2                       **C**                   A word can map to one
                                                  or more tokens; text
                                                  and tokenizer design
                                                  affect token count.

  3                       **B**                   An input that exceeds a
                                                  processing limit may be
                                                  truncated or require
                                                  chunking and retrieval.

  4                       **A**                   Subword methods help
                                                  balance vocabulary size
                                                  and representation of
                                                  rare words.

  5                       **C**                   Token IDs identify
                                                  entries in a tokenizer
                                                  vocabulary; they are
                                                  not word counts or
                                                  final answers.

  6                       **B**                   Special tokens or
                                                  markers can represent
                                                  boundaries, roles, and
                                                  sequence endings.

  7                       **C**                   Languages, scripts, and
                                                  tokenizer vocabularies
                                                  can produce different
                                                  token counts.

  8                       **A**                   Tokenization identifies
                                                  units and IDs;
                                                  embeddings provide
                                                  vector representations.
  -----------------------------------------------------------------------

## 10. Tokenization Interview Follow-up Questions

**Q1. What is tokenization?**\
Tokenization is the process of splitting text into smaller units called
tokens so that a language model can process it.

**Q2. Does one word always equal one token?**\
No. A word may be represented by one token or multiple tokens, depending
on the tokenizer.

**Q3. What is subword tokenization?**\
Subword tokenization represents text using smaller units that can handle
both common and uncommon words.

**Q4. What is the difference between BPE and WordPiece?**\
Both are subword tokenization methods, but they use different procedures
to learn or select subword units.

**Q5. How can tokenization affect API cost?**\
For APIs priced by token usage, more input or output tokens can increase
cost.

**Q6. Why can the same sentence have different token counts across
models?**\
Different models may use different tokenizers and vocabularies, leading
to different token splits.

------------------------------------------------------------------------

# Part B --- Context Window

## 11. What Is a Context Window?

**English definition:** A context window is the maximum amount of
tokenized information a model can consider in a single processing
context.

**Hindi:** Context window LLM ki woh limit hai jisme model ek baar mein
prompt, relevant conversation history aur doosri supplied information ko
process kar sakta hai.

### Simplified flow

`System instructions + user prompt + conversation history + documents`\
↓\
`Available context window (token budget)`\
↓\
`LLM processes the available context`\
↓\
`Generated response`

The exact context-window size depends on the model. In some models or
APIs, generated response tokens also need to fit within the overall
context budget.

## 12. Context Window Is Measured in Tokens

Consider a **hypothetical** model with a context window of 8,000 tokens.

  Content                                           Token usage (illustrative)
  ----------------------------------------------- ----------------------------
  System instructions                                                      500
  User prompt                                                            1,000
  Conversation history                                                   2,500
  Retrieved documents                                                    3,000
  **Total input**                                                    **7,000**
  **Remaining budget before other constraints**                      **1,000**

If the same budget must accommodate the generated answer, space may need
to be reserved for output.

*These numbers are only an example, not a specification for a real
model.*

## 13. What Happens When the Context Window Is Full?

Suppose a company has a 500-page HR policy document, but the entire
document cannot fit into the model's available context.

### Common approaches

-   **Truncation:** Extra text may be cut off, causing important
    information to be missed.
-   **Chunking:** Divide the document into smaller sections.
-   **Retrieval / RAG:** Retrieve the sections relevant to the user's
    question and supply them to the model.
-   **Summarization:** Condense long information while preserving
    important details.

**Capgemini scenario tip:** If a model misses information from a large
document, increasing temperature is not the appropriate fix for a
context-limit problem. Context management, chunking, or retrieval is
more relevant.

## 14. Context Window vs Persistent Memory

  -----------------------------------------------------------------------
  Context window                      Persistent memory
  ----------------------------------- -----------------------------------
  Information available in the        Information saved separately for
  current processing context.         possible use in future
                                      interactions.

  Has a token capacity limit.         Depends on the storage and
                                      retention rules of the system.

  Older information may fall outside  Saved information may be retrieved
  the available context.              later if the system supports it.
  -----------------------------------------------------------------------

**Interview point:** Having a context window does not automatically mean
an LLM permanently remembers every past conversation.

## 15. Context Window vs Tokenization

  -----------------------------------------------------------------------
  Tokenization                        Context window
  ----------------------------------- -----------------------------------
  Converts text into tokens.          Defines how much tokenized
                                      information can be considered in a
                                      processing context.

  Affects how text is split and       Limits the available context
  counted.                            capacity.

  Depends on the tokenizer.           Depends on the model and its
                                      configuration.
  -----------------------------------------------------------------------

**Example:** If a 10,000-word document becomes 12,000 tokens, it will
not fit as-is into an available input capacity of 8,000 tokens. The
exact token count depends on the tokenizer.

## 16. Context Window: Scenario-Based MCQs

Choose one answer per question before checking the answer key.

### Q1. Not enough room for the answer

A support assistant has a context limit of 8,000 tokens. The
instructions, chat history, and retrieved documents already consume
almost the entire budget, leaving insufficient room for the answer. What
is the best approach?

A. Increase temperature\
B. Manage context by removing irrelevant history or reducing retrieved
content while preserving relevant evidence\
C. Add more examples without removing anything\
D. Assume context windows count only user messages

### Q2. Missing exception in a large policy

An LLM answers a question about a 400-page policy but misses a crucial
exception near the end. The entire policy was too large to fit and was
truncated. What is the most suitable improvement?

A. Use retrieval or chunking to supply the relevant sections\
B. Increase temperature to maximum\
C. Convert all text to uppercase\
D. Remove the user question

### Q3. Context vs permanent memory

A model supports a large context window. A developer concludes that it
will permanently remember every conversation. Which statement is
correct?

A. Correct, because context is permanent storage\
B. Correct, if the temperature is zero\
C. Incorrect: context capacity does not itself provide persistent
memory\
D. Incorrect, because LLMs cannot process conversation history

### Q4. Same words, different tokens

Two prompts contain the same number of words, but one uses more tokens.
What is the most plausible reason?

A. A longer word count is hidden\
B. Tokenization differs due to language, word structure, punctuation, or
the tokenizer\
C. Context windows always assign one token per word\
D. The model has stopped training

### Q5. Large knowledge base

A team needs to answer questions about a large knowledge base and keep
responses grounded in the correct passages. What is usually more
practical than placing every document into every prompt?

A. Use retrieval to select relevant chunks for each question\
B. Always use the largest possible temperature\
C. Delete the context window\
D. Fine-tune after every customer question

## 17. Context Window MCQ Answer Key

  -----------------------------------------------------------------------
  Question                Answer                  Explanation
  ----------------------- ----------------------- -----------------------
  1                       **B**                   Manage the token budget
                                                  and leave room for
                                                  output; reduce
                                                  irrelevant context
                                                  without losing
                                                  important evidence.

  2                       **A**                   Chunking and retrieval
                                                  provide relevant
                                                  sections instead of
                                                  relying on a truncated
                                                  document.

  3                       **C**                   Context is available
                                                  for a processing task;
                                                  persistent memory
                                                  requires a separate
                                                  mechanism.

  4                       **B**                   Word count and token
                                                  count are not
                                                  equivalent; text and
                                                  tokenizer affect
                                                  tokenization.

  5                       **A**                   Retrieval selects
                                                  relevant evidence for a
                                                  query and helps manage
                                                  context limits;
                                                  retrieval quality still
                                                  needs evaluation.
  -----------------------------------------------------------------------

## 18. Context Window Interview Follow-up Questions

**Q1. What is a context window?**\
A context window is the maximum amount of tokenized information a model
can consider in a single processing context.

**Q2. Is a context window measured in words?**\
No. It is measured in tokens, and token count does not equal word count.

**Q3. What can be done when a document exceeds the context limit?**\
The application can use chunking, retrieval, summarization, or a model
with a larger context window, depending on the task.

**Q4. Does a larger context window guarantee a more accurate answer?**\
No. A larger context window allows more information to be supplied, but
it does not guarantee that the model will use every detail correctly.

**Q5. Does context window mean persistent memory?**\
No. Context is information available for the current processing task.
Persistent memory requires a separate storage or memory mechanism.

**Q6. Why use retrieval instead of sending every document?**\
Retrieval supplies the sections most relevant to a question, helping
manage context capacity. The retrieved content must still be relevant
and reliable.

------------------------------------------------------------------------

# Part C --- Final Revision

## 19. One-Minute Revision Sheet

### Tokenization

-   **Tokenization:** Text ko tokens mein divide karna.
-   **Token ID:** Tokenizer vocabulary mein token ka numerical
    identifier.
-   **Word-level:** Text ko complete words mein split karta hai.
-   **Character-level:** Text ko individual characters mein split karta
    hai.
-   **Subword:** Words ko smaller units mein represent kar sakta hai.
-   **BPE:** Frequent symbol-pair merging.
-   **WordPiece:** Learned criteria for subword selection.
-   **Unigram:** Probabilistic subword approach.
-   **Embeddings:** Numerical vector representations.
-   **Special tokens:** Can represent structure or control information.

### Context Window

-   **Context window:** Tokens ki maximum capacity for a processing
    context.
-   **Truncation:** Limit ke kaaran input ka kuch hissa cut ho jaana.
-   **Chunking:** Large document ko smaller parts mein divide karna.
-   **Retrieval / RAG:** Question ke liye relevant chunks retrieve
    karna.
-   **Persistent memory:** Information saved separately for possible
    future use.
-   **Key trap:** Context window does not automatically provide
    permanent memory.

## 20. Final Exam Traps

1.  **One word = one token** --- not always true.
2.  **Token count = word count** --- false.
3.  **Tokenization = embeddings** --- false; they perform different
    roles.
4.  **All tokenizers split text identically** --- false.
5.  **Increasing temperature fixes context overflow** --- false.
6.  **A large context window guarantees perfect recall** --- false.
7.  **A context window automatically remembers every past conversation**
    --- false.
8.  **Retrieval removes every possible hallucination** --- false;
    retrieval quality and answer grounding still matter.

## Recommended Next Topic

**Transformer Architecture & Self-Attention** --- study how token
representations are processed and how attention helps a model use
context.
