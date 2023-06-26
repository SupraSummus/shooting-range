Hello! It's another day, and I'd like to engage in a guided journaling session about my LLM app idea.

Several things have inspired me:

1. The Zettelkasten method. I read an article about it a long time ago, and it stuck with me. I tried creating my own Zettelkasten, but I got discouraged or bored. I'm not a very persistent person. However, the Zettelkasten method is old and was used without computers, relying only on paper, pen, and boxes. This shows that the idea works even without digital technology.

Using computer-aided Zettelkasten would be fantastic. I see Zettelkasten as an "external brain" or knowledge database. LLMs fit nicely here, as they can operate on this database of natural language notes.

2. My second source of inspiration is the search for an elegant solution without compromises. The starting question is, "How do we structure knowledge?" or "How do I organize my documents on a local file system?". Tree structures are too limiting, so we need a flat storage system. However, organizing documents this way raises questions about tags, their granularity, and consistency. Tags require too much effort, and there's no clear way to structure them. An alternative is links, like hyperlinks on the internet. This idea is employed in the Zettelkasten method, where notes are interlinked. I see no shortcomings with this approach, and it's an easy, bottom-up process.

3. Guided journaling, like what we're doing right now, is another inspiration. It's an excellent way of effortlessly getting thoughts from the mind into text, similar to the Pensieve from Harry Potter.

LLMs are a great tool for guiding these sessions.

The envisioned system has the following components:

A. A chat session with an AI prompter and a human interviewee. We frequently inject reminders for the AI prompter about its role and responsibilities to prevent drifting when the conversation gets lengthy.

B. A note-taker system that looks at the conversation and decides which notes to take. This AI is fed the most recent part of the prompter-interviewee conversation and objectives like "your task is to decide what to note down." We prompt the AI to respond in a structured way so we can parse the answers and save the notes.

C. A note-management AI that reviews and organizes notes. It can decide to split notes, interlink them, or signal that a note is missing crucial information. We prompt the AI with rules for structuring the database, like "each note should be able to stand alone; each note should contain a single idea." The AI's output should be parsable since real modifications to the database are performed by a rigid program.

D. A note-retrieval system that looks at the conversation between the prompter and interviewee and decides which notes to recall. It may crawl over links between notes to find complete information. This AI's output is also parsed by a program.

E. A note database, a rigid program that stores a flat table of notes. It uses embeddings to index the notes and enable semantic search.

As for challenges, the note-management AI (Component C) seems most complicated to me. I tried implementing something similar earlier but got bored before finishing it, or perhaps I was discouraged by the lack of results. I believe this AI can be implemented with the right prompt and maybe by splitting it into multiple stages like:

1. Evaluate note completeness
2. Evaluate note atomicity
3. Evaluate note links
4. Evaluate note back-links

Scalability is not an issue, as I want to build an open experiment rather than a commercial app.
