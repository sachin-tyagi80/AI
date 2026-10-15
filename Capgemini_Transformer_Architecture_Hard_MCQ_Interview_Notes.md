# Transformer Architecture — Basic to Advanced
**Capgemini AI Literacy Round | Concepts + Real-world scenarios + MCQs**

## Contents

1. [What is a Transformer?](#1-what-is-a-transformer)
2. [Why Transformers are important](#2-transformer-kyun-important-hai)
3. [Basic Transformer workflow](#3-transformer-ka-basic-workflow)
4. [Self-Attention and Q/K/V](#4-self-attention--sabse-important-concept)
5. [Multi-Head Attention](#5-multi-head-attention)
6. [Positional Information](#6-positional-encoding--positional-information)
7. [Feed-Forward Network, Residual Connections and Layer Normalization](#7-feed-forward-network-residual-connections-aur-layer-normalization)
8. [Encoder vs Decoder vs Encoder–Decoder](#8-encoder-vs-decoder-vs-encoderdecoder)
9. [Causal Masking](#9-causal-masking--gpt-style-models-mein)
10. [Capgemini-style Practice MCQs](#10-capgemini-style-scenario-based-mcqs)
11. [Hard Scenario-Based MCQs](#part-1-hard-scenario-based-mcqs)
12. [Interview Questions and Follow-ups](#part-2-transformer-interview-questions--follow-ups)
13. [Last-Minute Revision](#part-3-last-minute-revision)

---

Bhai, Tokenization aur Context Window ke baad ab hum Transformer Architecture padhenge. Ye LLMs ko samajhne ka important topic hai, kyunki GPT jaise modern language models Transformer architecture par based hain.
## 1. What is a Transformer?
English definition: A Transformer is a neural network architecture that uses attention mechanisms to process relationships between elements in a sequence, such as words or tokens.
Hindi: Transformer ek neural network architecture hai jo text ke tokens ke beech relationships samajhne ke liye attention mechanism ka use karta hai. Isse model context ke according words ka meaning samajhne aur relevant output generate karne mein help milti hai.
For example, sentence dekho:
“The student put the book on the table because it was heavy.”

Yahan “it” ka reference samajhne ke liye model ko surrounding context dekhna padta hai. Attention mechanism different tokens ke relationships ko model karne mein help karta hai.

sam-herman.github.io

## 2. Transformer kyun important hai?
Transformer se pehle bhi RNN aur LSTM jaise architectures use hote the. Transformers ne sequence processing ke liye attention-based approach introduce ki, jo training mein parallel processing ko support karti hai.
- Long-range relationships: Sequence mein door ke tokens ke beech relationships model kar sakta hai.
- Parallel processing: Training ke dauran sequence ke multiple token representations process kiye ja sakte hain.
- Contextual representations: Kisi token ka representation surrounding tokens ke basis par develop ho sakta hai.
- Scalability: Large language models ko train karne ke liye effective architecture provide karta hai.
Important: Transformer har task mein automatically perfect nahi hota; performance data, training, architecture aur inference setup par depend karti hai.
## 3. Transformer ka basic workflow
Input Text
“AI is useful”

Tokenization
Text → Tokens → Token IDs

Embeddings + Positional Information
Token representations and order information

Transformer Blocks
Attention + Feed-Forward Network

Output
For a generative LLM: predict next-token probabilities

Ye simplified workflow hai. Actual architecture model type ke hisaab se vary karti hai.
## 4. Self-Attention — sabse important concept
Self-attention Transformer ka key mechanism hai. Ye model ko input ke different tokens ke beech relationships calculate karne deta hai, taaki har token ki representation context se benefit le sake.
Example:
“The animal didn't cross the road because it was tired.”

Model ko “it” ka relationship “animal” ke saath identify karne mein attention help kar sakta hai.
Query, Key, Value (Q, K, V)
Self-attention mein teen important concepts hain:
Component	Simple meaning
Query (Q)	Current token kis information ko dhoondh raha hai
Key (K)	Har token ki information jisse relevance compare hoti hai
Value (V)	Information jo attention weights ke according combine hoti hai
Ek simple analogy: library mein tum ek question lekar jaate ho (Query), books ke titles/descriptions match karte ho (Keys), aur relevant books se information lete ho (Values).
Self-attention ka flow
Q
Query

K
Key

V
Value

Attention scores and weights
Calculate how strongly tokens relate

Context-aware token representations

Technical level par, scaled dot-product attention ka standard formula hai:
\[
\operatorname{Attention}(Q,K,V)=
\operatorname{softmax}\left(\frac{QK^\top}{\sqrt{d_k}}\right)V
\]

Abhi formula ratne se zyada iska meaning samjho: Query aur Key se relevance scores nikalte hain; softmax unhe weights mein convert karta hai; phir Values ko combine kiya jaata hai.
## 5. Multi-Head Attention
Ek hi attention operation se alag-alag types ke relationships capture karna limited ho sakta hai. Multi-head attention multiple attention heads use karta hai, jo different representation subspaces mein different relationships learn kar sakte hain.
Example sentence: “Riya gave Neha her book because she trusted her.”
Different attention heads pronouns, subjects, objects ya other relationships ke different patterns learn kar sakte hain. Ye fixed rule nahi hai ki har head ek hi specific role perform karega.
Exam tip: Self-attention tokens ke relationships model karta hai; multi-head attention multiple attention heads ka combined mechanism hai.
## 6. Positional Encoding / Positional Information
Attention alone inherently sequence order ko us tarah represent nahi karta jaise word order sentence meaning ko affect karta hai. Isliye Transformers ko positional information provide ki jaati hai.
Example:
- “Dog bites man.”
- “Man bites dog.”
Same words hain, lekin order badalne se meaning badal jaata hai.
Positional information model ko token positions ya sequence order distinguish karne mein help karti hai. Different architectures absolute positions, relative positions, rotary positional embeddings (RoPE) ya other methods use kar sakti hain.
## 7. Feed-Forward Network, Residual Connections aur Layer Normalization
Transformer block mein attention ke alawa bhi important components hote hain.
- Feed-Forward Network (FFN): Har token representation par additional learned transformations apply karta hai.
- Residual connection: Ek layer ka input uske output ke saath add karne ka path provide karta hai, jo deep networks ki training mein help karta hai.
- Layer normalization: Activations ko normalize karke training stability mein help kar sakti hai.
Typical simplified block:
Input → Attention → Residual/Normalization → FFN → Residual/Normalization
Actual order aur normalization placement architecture ke hisaab se differ kar sakti hai.
## 8. Encoder vs Decoder vs Encoder–Decoder
Capgemini assessment ke liye ye distinction zaroor yaad rakho.

Encoder-only
Input text ki contextual representations banane mein useful.
Example: BERT. Common uses include text classification and language understanding.

Decoder-only
Previous tokens ke context mein next token predict karta hai; causal attention future tokens ko attend karne se rokta hai.
Example: GPT. Common use: text generation.

Encoder–Decoder
Encoder input ko process karta hai; decoder encoder ki representations aur generated tokens ka use karke output banata hai.
Example: T5. Common use: translation and text-to-text tasks.

Important distinction: Har Transformer GPT jaisa nahi hota. GPT-style generative LLMs typically decoder-only hote hain, jabki BERT encoder-only architecture ka example hai.
## 9. Causal Masking — GPT-style models mein
Normal self-attention sequence ke tokens ke beech relationships consider kar sakta hai. Lekin autoregressive text generation mein model ko future target tokens dekhne nahi dene chahiye.
Causal masking future positions ko mask karta hai, taaki token prediction available previous context par based rahe.
Example:
Input prefix: The sky is
Model next token predict karta hai. Us prediction ke waqt woh training sequence ka future answer token attend nahi kar sakta.
Isliye GPT-style model sequence ko autoregressively generate kar sakta hai:
The → sky → is → blue
Har step par actual generation previous context aur model ke predictions par depend karti hai.
## 10. Capgemini-style Scenario-Based MCQs
Ab tricky workplace scenarios solve karo. Ye original practice questions hain, actual Capgemini exam se verified questions nahi.
### Transformer Practice Test
8/8 answered

Difficulty: Medium → Advanced · Select one answer per question.
## 1. A language model needs to determine which earlier words are relevant to the current word in a sentence. Which Transformer mechanism directly helps model these relationships?

A. Token counting

B. Self-attention

C. Temperature adjustment

D. Padding

Correct
Self-attention computes relationships between tokens and combines information based on attention weights.

## 2. An engineer is building a GPT-style model that predicts the next token. During training, the model must not use future target tokens when predicting the current position. Which technique is appropriate?

A. Causal masking

B. Increasing the context window

C. Word-level tokenization

D. Removing embeddings

Correct
Causal masking prevents a position from attending to future positions in autoregressive generation.

## 3. A team wants a model architecture commonly suited to classifying text using contextual representations of the input. Which option is the best match?

A. Decoder-only GPT architecture exclusively

B. Encoder-only architecture such as BERT

C. A tokenizer without a neural network

D. Temperature sampling alone

Correct
Encoder-only models such as BERT are commonly used for language understanding and classification tasks.

## 4. One attention head is not sufficient to capture all useful token relationships. Which Transformer component allows multiple attention operations to learn different patterns?

A. Multi-head attention

B. Context truncation

C. Padding token

D. Fine-tuning only

Correct
Multi-head attention combines multiple attention heads that can learn different relationships or representation patterns.

## 5. A translation system reads a source sentence, creates an internal representation, and generates a target-language sentence using that representation. Which architecture is a classic fit?

A. Encoder–decoder Transformer

B. Encoder-only model with no output-generation mechanism

C. Tokenizer-only pipeline

D. A vector database by itself

Correct
An encoder–decoder Transformer is a classic architecture for sequence-to-sequence tasks such as translation.

## 6. A model receives the same words in different orders, and the order changes the sentence meaning. Which component helps represent token positions or order?

A. Positional information

B. Temperature

C. Fine-tuning data alone

D. The number of output labels

Correct
Positional information lets a Transformer distinguish sequence positions or represent order.

## 7. A deep Transformer is difficult to train reliably. The team adds skip paths that combine a layer's input with its output. Which component are they using?

A. Residual connections

B. Tokenization

C. Causal masking only

D. Vector retrieval

Correct
Residual connections help information and gradients flow through deep neural networks.

## 8. An engineer says, “Self-attention and embeddings are the same because both involve vectors.” What is the best correction?

A. Embeddings represent tokens numerically; self-attention uses learned projections and attention weights to combine contextual information

B. Embeddings are only used after the final answer

C. Self-attention only splits words into subwords

D. Both terms mean context-window size

Correct
Embeddings provide vector representations; self-attention computes relationships and mixes information across token positions.

Score: 8/8
Retry test
### Quick revision sheet
Concept	One-line recall
Transformer	Attention-based neural network architecture
Self-attention	Models relationships between tokens
Q, K, V	Query, Key and Value
Multi-head attention	Multiple attention heads
Positional information	Represents token order or positions
Feed-forward network	Transforms token representations
Residual connection	Provides a skip path around a layer
Encoder-only	Example: BERT
Decoder-only	Example: GPT
Encoder–decoder	Example: T5
Causal masking	Blocks attention to future tokens
Tumhare roadmap mein next topic: LLM Training & Adaptation — pretraining, fine-tuning aur instruction tuning. Pehle ye Transformer MCQs attempt kar lo, phir aage badhenge.

Convert to PDF

capgimini based hard mcq 10 with ans and interviwer qustion  and follow up qustion in this topic

Bhai, ab Transformer Architecture ke 10 hard-level Capgemini AI Literacy MCQs karte hain. Questions workplace scenarios par based hain, options tricky hain aur har answer ke saath explanation bhi hai. Uske baad interviewer questions aur unke follow-ups bhi milenge.
## Part 1: Hard Scenario-Based MCQs
Topic: Self-Attention, Q/K/V, Causal Masking, Encoder–Decoder, Positional Information, Multi-Head Attention
Q1. Self-Attention vs Causal Masking
A company builds a GPT-style customer-support assistant. During testing, the model appears to use information from future target tokens when predicting the current token in a training sequence. This leads to unrealistically good training results but poor real-world generation.
What is the most appropriate architectural correction?
A. Increase the number of attention heads.
B. Apply causal masking so each position cannot attend to future positions.
C. Replace token embeddings with positional embeddings only.
D. Increase the temperature during training.
###
Answer: B — Apply causal masking.
Explanation: GPT-style autoregressive models must predict the next token using only the permitted preceding context. Causal masking prevents future-token information leakage. More attention heads or higher temperature do not solve this problem.
##
Interviewer follow-up: How is causal self-attention different from bidirectional self-attention?
##
Answer: Causal self-attention restricts each token from attending to future positions, while bidirectional self-attention can use both preceding and following tokens within the permitted input.

Q2. Query, Key and Value
An NLP engineer wants a model to determine which words in a long sentence are relevant to the token currently being processed. The model calculates compatibility scores between token representations and uses those scores to combine information.
Which sequence best describes the operation?
A. Values produce token IDs, Keys calculate temperature, and Queries generate embeddings.
B. Queries and Keys determine attention scores; softmax converts scores into weights; Values are combined using those weights.
C. Queries directly generate the final answer, while Keys and Values are only used during training.
D. Keys determine token positions, while Values prevent future-token access.
##
Answer: B.
Explanation: Query–Key compatibility determines how strongly tokens relate. Softmax converts scores into attention weights, which are applied to the Value vectors to produce contextual representations.
Interviewer follow-up: Why is the dot product scaled by \(\sqrt{d_k}\) in scaled dot-product attention?
##
Answer: When key dimensions are large, dot products can become large and make softmax distributions overly sharp. Scaling helps keep values in a more suitable range for stable optimization.

Q3. Multi-Head Attention
A legal-document analysis system misses relationships between pronouns, dates and named entities. The development team proposes using multiple attention heads instead of a single head.
Which statement best justifies this choice?
A. Each attention head is guaranteed to learn one specific semantic role.
B. Multiple heads can learn different attention patterns in different representation subspaces.
C. Multi-head attention removes the need for training data.
D. Multiple heads automatically increase the context window.
##
Answer: B.
Explanation: Multiple heads allow the model to represent different relationships or patterns. However, it is not guaranteed that one head will specialize in a specific role, and additional heads do not automatically expand the context window.
Interviewer follow-up: Does increasing the number of attention heads always improve model accuracy?
##
Answer: No. Performance depends on architecture, head dimensions, data, compute and training. More heads can increase cost without guaranteeing better results.

Q4. Positional Information
A Transformer-based sentiment system receives the following sentences:
- “The manager praised the employee.”
- “The employee praised the manager.”
The vocabulary contains the same words, but the meaning differs because the order changes.
Which architectural feature helps the model represent this difference?
A. Temperature scaling
B. Positional information combined with token representations
C. Increasing the number of output classes
D. Removing self-attention
Answer: B.
Explanation: Self-attention needs access to sequence-order information to distinguish different arrangements of the same tokens. Transformers use positional encodings, relative-position methods or other positional mechanisms, depending on the architecture.
##
Interviewer follow-up: Is sinusoidal positional encoding mandatory in every Transformer?
##
Answer: No. It is one approach. Modern architectures may use learned positional embeddings, relative position methods, RoPE or other techniques.

Q5. Encoder vs Decoder
A company needs to build two systems:
- System A classifies incoming customer feedback as positive, negative or neutral.
- System B generates a response one token at a time.
Which architecture pairing is the most appropriate among the options?
A. System A: encoder-only model; System B: decoder-only autoregressive model.
B. System A: decoder-only model is mandatory; System B: encoder-only model.
C. Both systems must use an encoder–decoder architecture.
D. Both systems must use a tokenizer without a Transformer.
Answer: A.
Explanation: Encoder-only architectures such as BERT are commonly suited to classification. Decoder-only models such as GPT are widely used for autoregressive generation. These are common design choices, not absolute restrictions; other architectures can perform these tasks too.
##
Interviewer follow-up: Why can a BERT-style encoder use information from both sides of a token?
##
Answer: Its bidirectional self-attention can attend to permitted tokens on both sides of the current position, making surrounding context available for representation learning.

Q6. Encoder–Decoder Cross-Attention
A translation model encodes a Hindi sentence and then generates its English translation. During decoding, the model must use information from the encoded Hindi sentence as well as the English tokens already generated.
Which component specifically allows the decoder to attend to the encoder's representations?
A. Positional encoding alone
B. Cross-attention
C. Causal masking alone
D. The tokenizer vocabulary
##
Answer: B — Cross-attention.
Explanation: In a classic encoder–decoder Transformer, the decoder uses cross-attention to access encoder outputs. Decoder self-attention separately models relationships among generated target-side tokens.
Interviewer follow-up: What is the difference between self-attention and cross-attention?
##
Answer: In self-attention, queries, keys and values originate from the same sequence or representation stream. In cross-attention, queries typically come from one stream and keys and values come from another, such as decoder states and encoder outputs.

Q7. Context Window vs Attention Mechanism
An application uses a Transformer with a fixed context limit. A developer adds more attention heads and expects the model to process twice as much input without any other architectural or system changes.
Which statement is most accurate?
A. The context window always doubles when attention heads double.
B. More heads automatically eliminate token limits.
C. Attention heads and context-window capacity are different design properties; more heads do not automatically expand the supported context.
D. Context windows are determined only by temperature.
##
Answer: C.
Explanation: Attention heads describe how attention is computed. Context capacity depends on the model architecture, positional mechanisms, training and serving constraints. Increasing head count alone does not guarantee a longer context window.
##
Interviewer follow-up: What challenges can arise when processing very long sequences with standard full self-attention?
Answer: Standard full self-attention generally has quadratic scaling in sequence length for attention-score computation. Long contexts can therefore increase memory use, computation and latency.

Q8. Residual Connections and Layer Normalization
A team trains a deep Transformer, but optimization becomes unstable as layers are stacked. Engineers investigate the network's residual pathways and normalization strategy.
Which explanation is most accurate?
A. Residual connections guarantee zero hallucinations.
B. Layer normalization replaces the need for attention.
C. Residual connections provide skip pathways, while normalization can help stabilize activation distributions and training.
D. Both components exist only to count tokens.
Answer: C.
Explanation: Residual connections help information and gradients flow through deep networks. Layer normalization supports training stability. Their exact arrangement differs between architectures, and neither guarantees perfect output.
##
Interviewer follow-up: Does a residual connection simply copy the input and discard the layer's output?
##
Answer: No. In a typical residual block, the input is combined with the transformed output, commonly through addition. Both pathways contribute to the resulting representation.

Q9. Transformer Parallelism
A developer claims that because Transformers support parallel processing during training, a standard autoregressive GPT model can generate every output token independently at inference time.
Which correction is best?
A. The claim is fully correct for every Transformer.
B. Training can process multiple positions in parallel with appropriate masking, but autoregressive generation generally depends on previously generated tokens.
C. Autoregressive models cannot use parallel hardware.
D. Parallel training means the model does not require tokenization.
##
Answer: B.

Explanation: Training computations across sequence positions can be parallelized while causal masking prevents access to future targets. During ordinary autoregressive inference, each new token depends on the preceding generated sequence, although optimized systems can parallelize other parts of the computation.
##
Interviewer follow-up: What is KV caching, and why is it useful?
Answer: KV caching stores previously computed Key and Value representations during autoregressive generation. It avoids recomputing them for the entire prefix at every step, reducing redundant computation and often improving inference speed.

Q10. Diagnosing a Transformer Failure
A company's document assistant produces fluent but incorrect answers. Engineers confirm that tokenization works and the Transformer processes the input correctly. However, the retrieved document passages are often irrelevant, and the model's answers are not checked against reliable sources.
What is the most appropriate conclusion?
A. A Transformer architecture guarantees factual correctness, so the issue must be the temperature.
B. The model should always be replaced with one having more attention heads.
C. Retrieval quality and grounding need improvement, and answer correctness should be evaluated; Transformer architecture alone does not guarantee factual accuracy.
D. Tokenization should be disabled so the model can reason directly over raw text.
##
Answer: C.
Explanation: A working Transformer can still produce incorrect answers. If the application uses RAG, retrieval quality and evidence grounding matter, and outputs should be evaluated for factual correctness. Temperature changes alone cannot fix missing or irrelevant evidence.
Interviewer follow-up: How would you evaluate whether the improved assistant is better?
##
Answer: Test it on representative questions and trusted reference answers. Measure answer correctness, relevance, groundedness, retrieval quality, safety, latency and cost. Include difficult and out-of-scope cases.
## Part 2: Transformer Interview Questions + Follow-ups
Ye questions interview mein tumhari conceptual clarity check karne ke liye useful hain. Har primary question ka short, interview-ready answer diya hai, phir ek follow-up question.
## 1. What is Transformer architecture, and why is it important for LLMs?

##
Interview answer
“A Transformer is a neural network architecture that uses attention mechanisms to model relationships between tokens. It supports parallel processing during training and can learn contextual representations, making it a foundation for many modern language models.”
##
Follow-up: What is the role of self-attention?
Answer: It calculates relationships between tokens and combines information to create context-aware representations.

## 2. Explain Query, Key and Value in simple terms.
##
Interview answer:
“Query represents what a token is looking for, Key represents information used to determine relevance, and Value contains information that is combined according to attention weights.”
##
Follow-up: How are attention weights calculated?
Answer: In scaled dot-product attention, Query–Key scores are scaled and passed through softmax to produce weights used to combine Values.

## 3. What is the difference between self-attention and cross-attention?
##
Interview answer:
“Self-attention models relationships within the same sequence or representation stream. Cross-attention allows one sequence or representation stream to attend to another, such as a decoder attending to encoder outputs.”
##
Follow-up: Where is cross-attention used in a classic Transformer?
Answer: In the decoder of an encoder–decoder Transformer, where decoder queries attend to encoder keys and values.

## 4. Why does a Transformer need positional information?
##
Interview answer:
“Attention mechanisms need information about token order to distinguish sequences with different arrangements. Positional information helps the model represent order and position.”
##
Follow-up: Name two positional approaches.
Answer: Learned positional embeddings and Rotary Positional Embeddings (RoPE).

## 5. What is the difference between encoder-only and decoder-only Transformers?
##
Interview answer:
“Encoder-only models such as BERT commonly use bidirectional context for language-understanding tasks. Decoder-only models such as GPT commonly use causal attention to generate text autoregressively.”
##
Follow-up: Why does GPT use causal masking?
Answer: To prevent a token prediction from accessing future target tokens.

## 6. What is multi-head attention?
##
Interview answer:
“Multi-head attention runs multiple attention operations in parallel. Each head can learn different relationships or patterns, and their outputs are combined.”
##
Follow-up: Does each head have a guaranteed specific role?
Answer: No. Heads may specialize, but their individual roles are not guaranteed.

## 7. Why can long-context processing be computationally expensive?
##
Interview answer:
“Standard full self-attention compares tokens across a sequence. Its attention computation and memory requirements can grow quadratically with sequence length, making long contexts expensive.”
##
Follow-up: Name one way to reduce the practical cost.
Answer: Use optimized attention implementations, efficient attention architectures, or retrieval to process only relevant context.

## 8. Why can a Transformer generate incorrect answers despite using attention?
##
Interview answer:
“Attention helps model relationships between tokens, but it does not guarantee factual correctness. Errors can result from training data, model limitations, missing evidence or poor retrieval.”
##
Follow-up: How can a document-based AI assistant reduce this risk?
Answer: Improve retrieval, ground answers in trusted documents, provide source references where appropriate, and evaluate the answers against reliable evidence.

## Part 3: Last-minute revision
### Must-remember concepts

- Self-attention → relationships between tokens.
- Q/K/V → relevance calculation and information combination.
- Multi-head attention → multiple attention patterns.
- Positional information → token order.
- Causal masking → prevents access to future positions.
- BERT → encoder-only example.
- GPT → decoder-only example.
- T5 → encoder–decoder example.
- KV cache → reuses prior Key/Value computations during generation.
- Transformer ≠ guarantee of factual accuracy.

Recommended next step: Transformer ke baad tumhare roadmap mein LLM Training & Adaptation aata hai—pretraining, fine-tuning, instruction tuning, aur inke beech differences. Us topic ko bhi hard scenario-based MCQs aur interviewer follow-ups ke saath cover karenge.
