Tokenization --- 
Basic to Advanced Capgemini AI Literacy Round \|
1. What is Tokenization? Definition
(English): Tokenization is the process of breaking text into smaller
units called tokens so that a language model can process the text.
Hindi: Tokenization mein text ko chhote units, yaani tokens, mein divide
kiya jaata hai. Ye tokens words, word ke parts, punctuation marks ya
doosre text units ho sakte hain. Example: Text → Tokens I love AI!
Tokenizer

I love AI !

Illustrative example: actual tokens tokenizer aur model ke hisaab se
alag ho sakte hain.

Important: One token does not always equal one word. - cat ek token ho
sakta hai. - unbelievable ek token ya multiple tokens ho sakta hai. -
Punctuation, numbers aur spaces bhi tokenization ko affect kar sakte
hain. - Tokenization language aur tokenizer ke according change hoti
hai. 2. Why do LLMs need tokenization? Computers language models ko
directly human-style words ki tarah process nahi karte. Text ko tokens
mein convert kiya jaata hai, phir tokens ko numerical token IDs mein map
kiya jaata hai. Input text: Hello world!

Tokenization: Hello · world · !

Token IDs: \[ID₁, ID₂, ID₃\]

Model processing and prediction

Token IDs sirf illustrative hain---actual IDs tokenizer ki vocabulary
par depend karte hain. Tokenization ke main purposes: 1. Text ko model
ke liye manageable units mein represent karna. 2. Words ke saath
unfamiliar words aur word-parts ko handle karna. 3. Model input aur
output ko token sequences ke roop mein represent karna. 4.
Context-window limits aur token-based usage ko manage karna. 3. Types of
Tokenization

A. Word-level tokenization Text ko complete words mein divide karna.
Example: I love AI → I \| love \| AI Limitation: New ya rare words ke
liye vocabulary bahut badi ho sakti hai.

B. Character-level tokenization Text ko individual characters mein
divide karna. Example: cat → c \| a \| t Limitation: Sequence bahut
lambi ho sakti hai aur characters ke beech meaning samajhna model ke
liye harder ho sakta hai.

C. Subword tokenization Words ko smaller meaningful ya frequently
occurring units mein split karna. Example: unbelievable → un \| believ
\| able (illustrative). Advantage: Vocabulary size aur rare words ko
handle karne ke beech balance provide karti hai. Modern LLMs mein
subword ya related tokenization methods common hain.

Exam tip Agar question poochhe ki modern LLMs unfamiliar words ko kaise
handle kar sakte hain, toh subword tokenization usually strong answer
hota hai. 4. Advanced tokenization methods Ye names pehchaan kar rakhna
useful hai: Method Key idea BPE (Byte Pair Encoding) Frequent symbol
pairs ko repeatedly merge karke vocabulary banata hai. WordPiece Subword
units select karta hai; BERT jaise models mein use hua hai. Unigram
Language Model Candidate subword vocabulary se units select karta hai
using a probabilistic model. Byte-level tokenization Bytes ko underlying
units ki tarah use kar sakti hai; kuch unseen text ko handle karne mein
helpful hai. Capgemini focus: Har algorithm ki mathematics ratne se
pehle unka basic difference, purpose aur use case samjho. 5. Special
tokens Tokenization sirf ordinary words ko split karna nahi hai. Kuch
models special tokens bhi use karte hain. Examples: - End-of-sequence
(EOS): Sequence ke end ko indicate kar sakta hai. -
Beginning-of-sequence (BOS): Sequence ki beginning mark kar sakta hai. -
Padding token: Batch processing mein sequences ki lengths align karne ke
liye. - Unknown token (UNK): Kuch tokenizers mein unrecognized unit ke
liye. - Role/format markers: Kuch chat models mein messages aur
structured output ko mark karne ke liye. Special tokens model aur
tokenizer ke hisaab se differ karte hain; har model sab tokens use nahi
karta. Scenario: Chatbot ko prompt mein system instruction, user message
aur assistant response ke boundaries samajhni hain. Special tokens ya
message markers model ko structure represent karne mein help kar sakte
hain. 6. Tokenization vs Embeddings Ye dono concepts confuse mat
karna---interviews mein difference poochha ja sakta hai.

Tokenization Text ko tokens mein divide karti hai aur tokenizer unhe
token IDs se map karta hai.

Embeddings Tokens ya doosre inputs ko numerical vectors mein represent
karti hain, jinhe model computation mein use kar sakta hai.

Yaad rakhne ka simple formula: Text → Tokens → Token IDs → Embedding
vectors → Model processing Real architectures mein implementation
details vary kar sakti hain, lekin ye useful conceptual pipeline hai. 7.
Token count aur Context Window LLMs ki input capacity generally tokens
mein measure hoti hai, sirf words ya characters mein nahi. - Prompt mein
instructions, user input aur supplied document tokens consume karte
hain. - Model ke context-window budget mein conversation history aur,
model ke hisaab se, generated output bhi count ho sakte hain. - Agar
input limit se bada ho, toh system kuch text truncate kar sakta hai ya
document ko chunks mein process kar sakta hai. - Same number of words
different languages ya tokenizer ke hisaab se different token counts
produce kar sakte hain. Example: Ek company ka 300-page manual ek hi
prompt mein fit nahi ho raha. Practical solution ho sakta hai document
ko chunks mein split karna, relevant sections retrieve karna, aur phir
unke basis par answer generate karna. Dhyan rahe: Token count words ki
exact count nahi hoti. "One token = one word" galat generalization hai.
8. Capgemini-style Scenario-Based MCQ Test Ab concepts ki practice karte
hain. Ye original practice questions hain, actual Capgemini exam ke
verified questions nahi. Pehle khud solve karna; answers abhi reveal
nahi kiye hain. Tokenization Practice 8/8 answered

Difficulty: Basic → Advanced · Select one answer for each question. 1. A
customer support LLM receives the word "unhappiness," which is not
present as a complete word in its vocabulary. The model still needs to
process it. Which approach can help?

A. Reject the input because the complete word is unknown

B. Split the word into available subword units

C. Convert the whole sentence directly into embeddings without
tokenization

D. Increase temperature

Correct Subword tokenization can represent an unfamiliar word using
smaller units already present in the vocabulary.

2.  A developer assumes that a 100-word prompt always uses exactly 100
    tokens. Why is this assumption incorrect?

A. Tokens only count punctuation

B. Every word always maps to two tokens

C. Token counts depend on the tokenizer, text, language and word
structure

D. Token counts are determined only by temperature

Correct A word may map to one or multiple tokens, and punctuation,
language and tokenizer design also affect token count.

3.  An LLM application sends a very long company policy document to the
    model, but the end of the document is missing from the processed
    input. What is the most relevant concern?

A. The model has too many parameters

B. Input truncation or context-window limits

C. The temperature is too low

D. Embeddings have converted words into characters

Correct Inputs that exceed a processing limit may be truncated or
require chunking and retrieval.

4.  A team wants to reduce the vocabulary size compared with word-level
    tokenization while still representing rare words. Which approach is
    generally suitable?

A. Subword tokenization

B. Only word-level tokenization

C. Removing all punctuation

D. Increasing the model's temperature

Correct Subword methods balance vocabulary size with the ability to
represent rare or unfamiliar words.

5.  A developer sees token IDs such as \[1542, 982, 27\] after
    preprocessing a sentence. What do these numbers represent?

A. The model's final answer

B. Embedding dimensions only

C. Numerical IDs assigned to tokens by a tokenizer

D. The number of words in the sentence

Correct Token IDs identify entries in the tokenizer's vocabulary; they
are not word counts or final answers.

6.  A chatbot needs to distinguish message boundaries and mark the end
    of a sequence. Which concept is most relevant?

A. Temperature scaling only

B. Special tokens or message markers

C. Word frequency alone

D. Increasing context length

Correct Special tokens or markers can represent boundaries, roles and
sequence endings, depending on the model.

7.  A team processes customer feedback in several languages. Two reviews
    have the same number of words but different token counts. What is
    the best explanation?

A. One review must be corrupted

B. All tokenizers use one token per word

C. Language and tokenizer behavior can change how text is split

D. The model always counts emojis as sentences

Correct Different languages, scripts and tokenizer vocabularies can
produce different token counts for similar word counts.

8.  An engineer says, "Tokenization and embeddings are the same because
    both convert text into numbers." Which correction is best?

A. Tokenization splits text and maps units to IDs; embeddings represent
tokens or inputs as vectors

B. Embeddings split words, while tokenization generates the final answer

C. Both are identical operations in every model

D. Tokenization is only used during training

Correct Tokenization identifies units and their IDs; embeddings provide
vector representations used in model computation.

Score: 8/8 Try Again Quick revision --- exam se pehle yaad rakhna -
Tokenization = text ko tokens mein divide karna. - Token ID = vocabulary
mein token ka numerical identifier. - Subword tokenization = rare words
ko smaller units se represent karne mein useful. - Embedding = numerical
vector representation. - Context window = model ke context mein handle
hone wale tokens ki limit. - Truncation = limit ke kaaran input ka kuch
hissa cut ho jaana. - BPE, WordPiece aur Unigram = subword tokenization
se related methods. Agla logical topic tumhare roadmap ke according
Transformer Architecture & Self-Attention hai. Pehle MCQs submit kar lo,
phir hum next topic par chalenge.

Convert to PDF

context window

Bhai, ab Context Window ko Capgemini AI Literacy round ke liye basic se
advanced tak samajhte hain, kyunki ye LLM aur Tokenization ka important
concept hai. 1. What is a Context Window? English definition: A context
window is the maximum amount of tokenized information a model can
consider in a single processing context. Hindi: Context window LLM ki
woh limit hai jisme model ek baar mein prompt, relevant conversation
history aur doosri supplied information ko process kar sakta hai. Input
to LLM System instructions + user prompt + conversation history +
documents

Context window (token limit)

LLM processes the available context

Generated response

Exact context-window size model par depend karti hai. Aur kuch models
mein generated response ke tokens bhi total available context budget ka
hissa hote hain. 2. Context window words mein nahi, tokens mein measure
hoti hai Example ke liye, maan lo ek hypothetical LLM ki context window
8,000 tokens hai. Content Token usage (illustrative) System instructions
500 User prompt 1,000 Conversation history 2,500 Retrieved documents
3,000 Total input 7,000 Remaining budget 1,000 Agar model ko isi context
budget mein answer generate karna hai, toh output ke liye bhi jagah
rakhni pad sakti hai. Important: Ye sirf samjhane ke liye example hai,
kisi actual model ki specification nahi. 3. Context window full ho jaaye
toh kya hota hai? Maan lo company ke paas 500-page HR policy document
hai aur poora document model ki context limit mein fit nahi ho raha.
Possible solutions: - Truncation: Extra text cut ho sakta hai, jisse
important information miss ho sakti hai. - Chunking: Document ko smaller
parts mein divide karna. - Retrieval / RAG: User ke question se relevant
chunks retrieve karna. - Summarization: Long information ko concise form
mein reduce karna, lekin important details preserve karni hongi.
Capgemini scenario tip: Agar question kahe ki model ek bade document ka
important content miss kar raha hai, toh sirf temperature badhana
solution nahi hai. Context management, chunking ya retrieval zyada
relevant ho sakte hain. 4. Context window vs memory In dono ko confuse
mat karna. Context window Persistent memory Current processing context
mein available tokens Information jo system alag se future interactions
ke liye save kar sakta hai Limited capacity hoti hai Storage aur
retention rules par depend karta hai Old conversation context se bahar
ho sakti hai Saved information baad mein retrieve ki ja sakti hai, agar
feature available ho Interview point: LLM ki context window hona
automatically ye guarantee nahi karta ki woh har purani conversation ko
permanently yaad rakhega. 5. Context window vs tokenization -
Tokenization: Text ko tokens mein convert karna. - Context window: Model
ek processing context mein kitne tokens handle kar sakta hai, uski
limit. Example: Agar 10,000-word document 12,000 tokens mein convert
hota hai aur model ki available input capacity 8,000 tokens hai, toh
document ko as-is fit karna possible nahi hoga. Exact token count
tokenizer par depend karega.

6.  Capgemini-style scenario MCQs Practice Test 5/5 answered

Choose the best answer. Answers and explanations appear after
submission. 1. A support assistant has a context limit of 8,000 tokens.
The instructions, chat history and retrieved documents already consume
almost the entire budget, leaving insufficient room for the answer. What
is the best approach?

A. Increase temperature

B. Manage the context by removing irrelevant history or reducing
retrieved content while preserving relevant evidence

C. Add more examples without removing anything

D. Assume context windows count only user messages

Correct The application must manage the token budget and leave room for
output. Irrelevant context can be reduced without discarding important
evidence.

2.  An LLM answers a question about a 400-page policy but misses a
    crucial exception found near the end. The entire policy was too
    large to fit and was truncated. What is the most suitable
    improvement?

A. Use retrieval or chunking to supply the relevant sections

B. Increase temperature to maximum

C. Convert all text to uppercase

D. Remove the user question

Correct Chunking and retrieval help provide relevant sections instead of
relying on a truncated document.

3.  A model supports a large context window. A developer concludes that
    it will permanently remember every conversation. Which statement is
    correct?

A. Correct, because context is permanent storage

B. Correct, if the temperature is zero

C. Incorrect: context capacity does not itself provide persistent memory

D. Incorrect, because LLMs cannot process conversation history

Correct Context is the information available for a processing task.
Persistent memory requires a separate storage or memory mechanism.

4.  Two prompts contain the same number of words, but one uses more
    tokens. What is the most plausible reason?

A. A longer word count is hidden

B. Tokenization differs due to language, word structure, punctuation or
the tokenizer

C. Context windows always assign one token per word

D. The model has stopped training

Correct Word count and token count are not equivalent; tokenization
depends on the text and tokenizer.

5.  A team needs to answer questions about a large knowledge base and
    keep responses grounded in the correct passages. What is usually
    more practical than placing every document into every prompt?

A. Use retrieval to select relevant chunks for each question

B. Always use the largest possible temperature

C. Delete the context window

D. Fine-tune after every customer question

Correct Retrieval provides relevant evidence for each query and helps
manage context limits, although retrieval quality must still be
evaluated.

Score: 5/5
