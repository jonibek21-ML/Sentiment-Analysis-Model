# 🌍 Transformer Translation Model (Toy Dataset)

Ushbu loyiha **Transformer arxitekturasi** asosida oddiy **toy dataset** yordamida tarjima modelini **0 dan boshlab PyTorch’da implementatsiya qilish** uchun yozildi.

Model quyidagi asosiy qismlardan iborat:

* Tokenization
* Embedding
* Positional Encoding
* Encoder
* Decoder
* Training pipeline
* Greedy decoding
* Attention visualization

---

# 📦 Dataset (Toy Translation Data)

Model kichik test dataset ustida ishlaydi.

Misol:

```
hello → salom
i am student → men talaba
how are you → qalaysan
```

Dataset maqsadi:

* Transformer pipeline tushunish
* Encoder–Decoder ishlashini ko‘rish
* Attention mexanizmini vizual tekshirish

---

# 🔤 Tokenization

Matnlar quyidagi bosqichdan o‘tadi:

* lowercase qilish
* split orqali tokenlarga ajratish
* vocabulary yaratish
* token → index mapping

Misol:

```
hello world → [2, 5]
```

Maxsus tokenlar:

```
<pad>
<sos>
<eos>
<unk>
```

---

# 🧠 Embedding Layer

Har bir token **embedding vector** ga o‘tkaziladi:

```
(token_id) → embedding vector
```

Embedding dimension:

```
d_model = 512
```

Output shape:

```
(batch_size, seq_len, d_model)
```

Embedding modelga:

* semantic meaning
* context learning

imkonini beradi.

---

# 📍 Positional Encoding

Transformer sequence tartibini bilmaydi.

Shuning uchun positional encoding qo‘shiladi:

```
embedding + positional_encoding
```

Bu modelga:

* token order
* sentence structure

haqida ma'lumot beradi.

Sinusoidal positional encoding ishlatilgan.

---

# 🏗 Encoder

Encoder quyidagi qismlardan tashkil topgan:

```
Multi-Head Attention
+
Add & Norm
+
Feed Forward Network
+
Add & Norm
```

Encoder vazifasi:

```
source sentence → contextual representation
```

Output:

```
(batch_size, src_len, d_model)
```

---

# 🏗 Decoder

Decoder quyidagi bloklardan iborat:

```
Masked Multi-Head Attention
+
Encoder-Decoder Attention
+
Feed Forward
```

Decoder vazifasi:

```
target sentence generation
```

Decoder oldingi tokenlarga qarab keyingi tokenni predict qiladi.

---

# ⚙ Training Pipeline

Training bosqichlari:

```
Tokenize
→ Pad sequence
→ Embedding
→ Positional Encoding
→ Encoder
→ Decoder
→ Linear
→ Softmax
```

Loss function:

```
CrossEntropyLoss
```

Optimizer:

```
Adam
```

Teacher forcing ishlatilgan.

---

# 🔍 Greedy Decoding

Inference vaqtida model quyidagi algoritm orqali tarjima qiladi:

```
<sos>
↓
predict next token
↓
append token
↓
repeat until <eos>
```

Bu usul:

```
Greedy Search
```

deb ataladi.

Har bosqichda eng katta ehtimollikdagi token tanlanadi.

---

# 📊 Attention Visualization

Attention weights vizual ko‘rinishda chiqariladi.

Bu orqali model:

```
qaysi token qaysi tokenni kuzatyapti
```

ko‘rish mumkin.

Misol:

```
hello → salom
```

attention map orqali token alignment tekshiriladi.

Visualization yordam beradi:

* modelni interpret qilish
* encoder-decoder bog‘lanishini tushunish
* training sifatini baholash

---

# 🚀 Model Pipeline Summary

Transformer pipeline:

```
Input sentence
→ Tokenization
→ Embedding
→ Positional Encoding
→ Encoder
→ Decoder
→ Linear Layer
→ Softmax
→ Output sentence
```

Model kichik dataset ustida ishlaydi va Transformer arxitekturani tushunish uchun educational loyiha sifatida yozilgan.
