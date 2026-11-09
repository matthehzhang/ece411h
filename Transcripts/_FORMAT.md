# Transcript node format (ECE 411H, F26)

Every file in Transcripts/ is a faithful, complete, machine-searchable transcription of ONE source document
(a PDF, often handwritten or image-only). Rules:

1. Frontmatter (YAML):
   ---
   course: ECE 411H
   kind: <refresher-notes | transform-table | problem-video | problem-set | problem-set-solution | past-exam | graded-exam>
   source: <relative path of the original file from the ece411 root>
   source_pages: <n>
   author: <Prof. Ed Yu | TA | [student] | Ulaby/Maharbiz/Furse | unknown>
   unit: <exam2 | final>
   topics: [lowercase, kebab-case, tags]
   transcribed: 2026-11-06
   method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
   ---
2. Then `# <Title>` and a 3–6 line **Summary** of what the document contains and why it matters for the exam.
3. Then the body, page by page, headed `## Page N`. Transcribe EVERYTHING written: every equation, every label,
   every number, every circled or starred item, every margin note. Do not summarize, do not skip "obvious" steps,
   do not paraphrase derivations. Completeness beats brevity here.
4. Math in LaTeX ($...$ inline, $$...$$ display), same style as ece411/Lectures/*.md.
5. Figures and circuits: describe in words precisely enough to redraw: topology (series/parallel, which node
   connects to which), component labels and values, source type and polarity, which quantity is marked as
   output, axes and curve shape for plots, and any annotated values. Prefix with **Figure:**.
6. Grader marks / strike-throughs / corrections: transcribe both the original and the correction, mark which is which.
7. If a word or symbol is unreadable, write `[illegible]`; if you have a confident guess, `[illegible, likely: X]`.
   Never invent content.
8. End with `## Index terms` : a flat comma-separated list of every concept, formula name, component, and problem
   number appearing in the document (for grep).
