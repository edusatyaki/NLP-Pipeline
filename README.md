# The Classic NLP Pipeline

An interactive teaching site for the classic Natural Language Processing pipeline — from raw
text to numeric vectors. Built from a set of lecture notes, with every stage runnable in the
browser.

**Live:** https://edusatyaki.github.io/NLP-Pipeline/
**Slides:** https://edusatyaki.github.io/NLP-Pipeline/deck.html

## What is here

| File | What it is |
| --- | --- |
| `index.html` | The full notes — fourteen sections, scrollable, with live demos and diagrams |
| `deck.html` | The same material as a 52-slide lecture deck for presenting |

Both are single self-contained files. No build step, no dependencies, no network calls —
open the file and it works.

## The pipeline it covers

Raw text → normalization → tokenization → POS tagging → NER → lemmatization →
stopword removal → vectorization, plus parsing, pipeline ordering, and the jump from
Bag-of-Words through TF-IDF to Word2Vec, GloVe and contextual embeddings.

## What runs live in the page

Everything computes in the browser as you type:

- **The pipeline machine** — type any sentence and step through all seven stages, watching
  tokens get split, tagged, collapsed, dropped and finally counted into a vector. Ticking
  "lowercase now" at stage 1 makes entity recognition find nothing at stage 5, which is the
  whole argument for the ordering rules.
- **BPE merger** — run byte pair encoding one merge at a time on your own corpus
- **Stem vs. lemma** — compare both on any word, with the POS tag that drives the lemma
- **Stopword picker** — click words in and out and watch the meaning flip
- **Bag of Words ⇄ TF-IDF** — a live matrix over three editable documents, with the idf row
- **Embedding space** — click two words for cosine similarity, or run `king − man + woman`

## For students

Every section opens with an **In plain words** box, ends with a **Words used in this
section** panel, and every technical term is dotted-underlined in the prose — hover or tap
it for a plain-English meaning. There is a full 87-term decoder at the foot of the page.

## A note on the demos

The tagger, lemmatizer, stemmer and entity recognizer in this page are small teaching
implementations — a lexicon plus suffix and capitalization rules — not NLTK or spaCy. They
behave the way the real tools behave on ordinary sentences, and they fail in the same
characteristic places, which is the point. Production code samples in the notes use the
real libraries.

## Running it locally

```bash
python3 -m http.server 8101
```

Then open http://localhost:8101 — or just open `index.html` directly in a browser.

## Presenting from the deck

Arrow keys or space to move, `F` for full screen, `N` to jump to the notes, `Home` / `End`
for the ends. Swipe works on a tablet. The slide number is in the URL, so you can bookmark
where you left off.
