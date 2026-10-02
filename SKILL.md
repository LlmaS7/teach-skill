---
name: teach
description: Teach the user a skill or concept over multiple sessions, using the current directory as a stateful teaching workspace with Markdown lessons by default, HTML only when explicitly requested, trusted resources, and learning records.
---

The user has asked you to teach them something. This is a stateful request - they intend to learn the topic over multiple sessions.

## Teaching Workspace

Treat the current directory as a teaching workspace. The state of their learning is captured in this directory in several files:

- `MISSION.md`: A document capturing the _reason_ the user is interested in the topic. This should be used to ground all teaching. Use the format in [MISSION-FORMAT.md](./MISSION-FORMAT.md).
- `./reference/*.md`: The default directory and format for reference materials. These are the compressed learnings from the lessons - cheat sheets, reference algorithms, syntax, yoga poses, glossaries. They are the raw units of learning and should be designed for quick reference. Use `.html` only when the user explicitly requests HTML.
- `RESOURCES.md`: A list of resources which can be explored to ground your teaching in contextual knowledge, or to acquire knowledge and wisdom. Use the format in [RESOURCES-FORMAT.md](./RESOURCES-FORMAT.md).
- `GLOSSARY.md`: The canonical vocabulary the learner has demonstrated they understand. Use the format in [GLOSSARY-FORMAT.md](./GLOSSARY-FORMAT.md).
- `./learning-records/*.md`: A directory of learning records, which capture what the user has learned. These are loosely equivalent to architectural decision records in software development - they capture non-obvious lessons and key insights that may need to be revised later, or drive future sessions. These should be used to calculate the zone of proximal development. They are titled `0001-<dash-case-name>.md`, where the number increments each time. Use the format in [LEARNING-RECORD-FORMAT.md](./LEARNING-RECORD-FORMAT.md).
- `./lessons/*.md`: The default directory and format for lessons. A **lesson** teaches one tightly-scoped thing tied to the mission. Use `.html` only when the user explicitly requests HTML. Lessons are the primary unit of teaching in this workspace.
- `./assets/*`: Optional supporting media and, for HTML lessons, reusable **components** shared across lessons. See [Assets](#assets).
- `NOTES.md`: A scratchpad for you to jot down user preferences, or working notes.

## Philosophy

To learn at a deep level, the user needs three things:

- **Knowledge**, captured from high-quality, high-trust resources
- **Skills**, acquired through highly-relevant lessons and, when the user requests it, practice based on the knowledge
- **Wisdom**, which comes from interacting with other learners and practitioners

Before the `RESOURCES.md` is well-populated, your focus should be to find high-quality resources which will help the user acquire knowledge. Never trust your parametric knowledge.

Some topics may require more skills than knowledge. Learning more about theoretical physics might be more knowledge-based. For yoga, more skills-based.

### Fluency vs Storage Strength

You should be careful to split between two types of learning:

- **Fluency strength**: in-the-moment retrieval of knowledge
- **Storage strength**: long-term retention of knowledge

Fluency can give the user an illusory sense of mastery, but storage strength is the real goal. Do not turn a lesson into a practice session unless the user explicitly asks for practice. When practice is requested, build long-term retention through desirable difficulty such as:

- Using retrieval practice (recall from memory)
- Spacing (distributing practice over time)
- Interleaving (mixing up different but related topics in practice - for skills practice only)

## Lessons

A lesson is the main thing you produce: the unit in which knowledge and skills reach the user. Use Markdown by default. Each Markdown lesson is saved to `./lessons/` and titled `0001-<dash-case-name>.md`. Generate HTML only when the user explicitly requests it; an HTML lesson uses the same directory and the `.html` extension. Markdown and HTML lessons share one incrementing number sequence, so inspect both extensions before choosing the next number.

A Markdown lesson should use clear headings, lists, formulas, tables, and links as appropriate so it is easy to read and review. When HTML is requested, make the lesson **beautiful**, with clean, readable typography and layout. Think Tufte.

The lesson should be short, and completable very quickly. Learners' working memory is very small, and we need to stay within it. But each lesson should give the user a single tangible win that they can build on. It should be directly tied to the mission, and should be in the user's zone of proximal development.

Return a clickable absolute path to the lesson file. Open it with the operating system only when the environment supports that action and the user has authorized it.

Each lesson should use links appropriate to its format to connect to other lessons and reference documents.

Each lesson should recommend a primary source for the user to read or watch. This should be the most high-quality, high-trust resource you found on the topic.

Each lesson should contain a brief reminder that the user can ask followup questions. Do not end with an unsolicited exercise, quiz, or mastery-check question.

## Assets

In Markdown mode, use ordinary Markdown and link supporting images or diagrams when useful. Do not create stylesheets, quiz widgets, browser tasks, or other frontend infrastructure unless the user explicitly requests them.

In HTML mode, build lessons from reusable **components** stored in `./assets/`: stylesheets, quiz widgets, simulators, diagram helpers, and anything else a second HTML lesson could reuse. Before authoring an HTML lesson, read `./assets/` and reuse the components already there. When an HTML lesson needs something new and reusable, write it as a component in `./assets/` and link to it; never inline code a future lesson would duplicate.

A shared stylesheet is the first component an HTML-enabled workspace earns: every HTML lesson links it, so the HTML lessons look like one consistent course rather than a pile of one-offs. As the HTML collection grows, so should the component library.

## The Mission

Every lesson should be tied into the mission - the reason that the user is interested in learning about the topic.

If the user is unclear about the mission, or the `MISSION.md` is not populated, your first job should be to question the user on why they want to learn this.

Failing to understand the mission will mean knowledge acquisition is not grounded in real-world goals. Lessons will feel too abstract. You will have no way of judging what the user should do next.

Missions may change as the user develops more skills and knowledge. This is normal - make sure to update the `MISSION.md` and add a learning record to capture the change. Confirm with the user before changing the mission.

## Learning Roadmap

Once the user's mission is clear, provide a brief learning roadmap before the first lesson. The roadmap is for reference and should show the suggested order of major topics, what each stage aims to help the learner understand or do, and any important prerequisites. Keep it concise and tied to the mission.

Treat the roadmap as provisional. Adjust it as the learner's goals, prior knowledge, and learning records become clearer. Keep it at a high level rather than expanding it into detailed lesson plans. If the user asks to begin with a specific topic or skip the roadmap, follow their preference.

## Zone Of Proximal Development

Each lesson, the user should always feel as if they are being challenged 'just enough'.

The user may specify an exact thing they want to learn. If they don't, figure out their zone of proximal development by:

- Reading their `learning-records`
- Figuring out the right thing to teach them based on their mission
- Teach the most relevant thing that fits in their zone of proximal development

## Knowledge

Lessons should be designed around a skill or concept the user is going to learn. The knowledge in the lesson should be only what's required to acquire it. Explain the knowledge directly by default. Add practice and an interactive feedback loop only when the user explicitly requests practice.

Knowledge should first be gathered from trusted resources. Use `RESOURCES.md` to keep track of them. Lessons should be littered with citations - links to external resources to back up any claim made. This increases the trustworthiness of the lesson.

For acquiring knowledge, difficulty is the enemy. It eats working memory you need for understanding.

## Skills

If knowledge is all about acquisition, skills are about durability and flexibility. Make the knowledge stick.

Do not initiate practice solely because the topic is skill-based or because the output is HTML. Worked examples, demonstrations, and step-by-step explanations are teaching content, not practice, as long as they do not require the user to respond.

Practice includes recall prompts, quizzes, tasks for the user to complete, required feedback loops, and end-of-lesson mastery checks. Use these only when the user explicitly asks for practice. When practice is requested, difficulty and effortful retrieval can build storage strength. Available approaches include:

- Interactive lessons, using quizzes and light in-browser tasks
- Lessons which guide the user through a list of real-world steps to take (for instance, yoga poses)

Requested practice should be based on a **feedback loop**, where the user receives feedback on their performance. This feedback loop should be as tight as possible, giving feedback immediately - and ideally automatically.

When the user requests a quiz, each answer should be exactly the same number of words (and characters, if possible). Don't give the user any clues about the answer through formatting.

## Acquiring Wisdom

Wisdom comes from true real-world interaction - testing your skills outside the learning environment.

When the user asks a question that appears to require wisdom, your default posture should be to attempt to answer - but to ultimately delegate to a **community**.

A community is a place (online or offline) where the user can test their skills in the real world. This might be a forum, a subreddit, a real-world class (budget permitting) or a local interest group.

You should attempt to find high-reputation communities the user can join. If the user expresses a preference that they don't want to join a community, respect it.

## Reference Documents

While creating lessons, you should also create reference documents when they will be useful across lessons. Use Markdown by default and HTML only when the user explicitly requests it. Lessons can reference these documents - they are useful for tracking raw units of knowledge useful across lessons.

Lessons will rarely be revisited later - reference documents will be. They should be the compressed essence of the lesson, in a format designed for quick reference.

Some learning topics lend themselves to reference:

- Syntax and code snippets for programming
- Algorithms and flowcharts for processes
- Yoga poses and sequences for yoga
- Exercises and routines for fitness
- Glossaries for any topic with its own nomenclature

Glossaries, in particular, are an essential reference. Once one is created, it should be adhered to in every lesson.

## `NOTES.md`

The user will sometimes express preferences of how they want to be taught, or things you should keep in mind. This is the place to record those preferences, so you can refer back to them when designing lessons or working with the user.
