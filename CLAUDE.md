# CSMC Trainer

## What it is
A personal practice site for Canadian Senior Mathematics Contest (CSMC) past problems, similar to AMC trainer sites. Built for me (Darren) to practice. Hosted free on GitHub Pages.

## Credit and rules
- CEMC past contests are licensed CC BY-NC 4.0.
- The site must credit "Problems © Centre for Education in Mathematics and Computing (CEMC), University of Waterloo", with a link to cemc.uwaterloo.ca/resources/past-contests, in the footer and on every question.
- Always free. No ads, no paywall.

## Questions data
- All questions live in `data/questions.json`.
- Source PDFs (contest + solutions) go in `source/`. They are only for transcribing and are never shown on the site.
- Each question looks like:
  ```json
  {
    "id": "2025-A3",
    "year": 2025,
    "part": "A",
    "number": 3,
    "topics": ["geometry"],
    "question": "LaTeX-ready text, math in $...$",
    "image": "images/2025-A3.png or null",
    "answer": "short answer (Part A only)",
    "solution": "official solution text, math in $...$"
  }
  ```
- Topics: algebra, geometry, number theory, combinatorics, probability, functions, sequences, logic.
- Math is written in LaTeX and rendered with KaTeX.
- Diagrams are cropped from the PDFs and saved as PNGs in `images/`.
- Transcribe math exactly. If something in a PDF is unclear, flag it instead of guessing.

## How the two parts work
- **Part A** (short answer): type an answer, the site checks it. Ignore spaces, and accept equivalent forms where possible (e.g. 1/2 = 0.5). There's always an "I was actually right" override in case the checker misses an equivalent form.
- **Part B** (full solution): work it out on paper, reveal the official solution, then mark yourself Correct / Partly / Wrong.

## Features
1. **Random practice**: one question at a time, random from whatever the filters allow.
2. **Filters**: by year, part (A/B), question number range, and topic.
3. **Timed full contest**: a whole year's CSMC in order, with the official time limit from the contest paper. Countdown timer, results summary at the end.
4. **Progress + stats**: track every attempt. Show % correct overall and by topic and part, a list of questions got wrong to retry, and a "flag for review" button.
- Progress saves in localStorage (key: `csmc-trainer-progress`), wrapped in try/catch. No accounts.

## Tech
- Plain HTML, CSS, JavaScript. No frameworks, no build step.
- KaTeX loaded from a CDN for math.
- Files: `index.html`, `css/style.css`, `js/` (split into clear files), `data/questions.json`, `images/`, `source/`.
- All paths relative and lowercase (GitHub Pages is case-sensitive).
- Clean, focused look: easy to read math, good on laptop and phone.

## Build order
1. Transcribe one contest year (2025) into `data/questions.json`
2. Question view: show one question with KaTeX math and its diagram
3. Answer checking (Part A) and solution reveal + self-marking (Part B)
4. Random practice + filters
5. Progress tracking + stats page
6. Timed full contest mode
7. Add more years

## Working with me
- I'm still learning to code. Explain what you changed in a few plain sentences.
- Build one feature at a time, then tell me how to test it with Live Server.
- Add short comments in the code so I can follow it.
- Don't commit or push. I'll do that. Suggest a commit message when a feature is done.
