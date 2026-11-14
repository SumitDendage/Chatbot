# Retrieval-Based Chatbot (TF-IDF + NLTK)

A lightweight question-answering chatbot that answers from a text document. It finds the sentence in its knowledge base that is most similar to your question using **TF-IDF vectors and cosine similarity** — no large language model required.

![Python](https://img.shields.io/badge/Python-3.9+-3776AB?logo=python&logoColor=white)
![NLTK](https://img.shields.io/badge/NLTK-tokenize%20%7C%20lemmatize-154F5B)
![scikit-learn](https://img.shields.io/badge/scikit--learn-TF--IDF-F7931E?logo=scikitlearn&logoColor=white)

## How it works

1. **Corpus** – `data_doc.txt` (text of the Wikipedia article on chatbots) is lower-cased and split into sentences with NLTK.
2. **Pre-processing** – punctuation is stripped, words are tokenised and lemmatised with WordNet.
3. **Greetings** – simple keyword rules answer "hello", "hi", etc.
4. **Retrieval** – the user's question is added to the sentence list, everything is vectorised with `TfidfVectorizer`, and the sentence with the highest cosine similarity to the question is returned. If nothing overlaps, the bot says it doesn't understand.
5. **Conversation loop** – type `bye` to exit, `thanks` to end politely.

```text
Hello! I am Learning Bot. Start typing your text after greeting to talk to me. For ending convo type bye!
> hello
Learning Bot: hi there
> what is a chatbot
Learning Bot: a chatbot (originally chatterbot)[1] is a software application or web interface designed to have textual or spoken conversations.
```

## Run it

```bash
git clone https://github.com/SumitDendage/Chatbot.git
cd Chatbot
pip install nltk scikit-learn numpy jupyter
jupyter notebook chatbot.ipynb
```

The notebook downloads the NLTK data it needs (`punkt_tab`, `wordnet`, `omw-1.4`) on first run. To build a bot for another topic, replace `data_doc.txt` with your own text.

## Files

| File | Purpose |
|---|---|
| `chatbot.ipynb` | Complete chatbot: pre-processing, greeting rules, retrieval and chat loop |
| `data_doc.txt` | Knowledge base the bot answers from |
| `chatbot.docx` | Project write-up |

## Ideas for improvement

- Replace TF-IDF with sentence embeddings (e.g. Sentence-Transformers) for semantic matching.
- Return the top-k passages to an LLM to generate fluent answers (retrieval-augmented generation).
- Wrap the bot in a small Streamlit or Flask UI.

## Author

**Sumit Dendage** · [GitHub](https://github.com/SumitDendage) · [LinkedIn](https://www.linkedin.com/in/sumit-dendage-636a50201) · [Medium](https://dendagesumitbalkrishna123.medium.com)
