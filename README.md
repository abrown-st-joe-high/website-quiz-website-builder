# Quiz Page Generator

Three files:

- **index.html** — the generator itself. Paste a sheet of questions, get back a self-contained quiz page.
- **styles.css** — the shared look for the generator and every quiz page. Upload once; edit it anytime to restyle every quiz at once.
- **example-quiz.html** — a sample quiz already generated from the "full" sample data, so you can see the finished product before making your own.

## One-time setup

1. Create a GitHub repo (or use an existing one).
2. Upload `index.html` and `styles.css` to the repo root.
3. In the repo: **Settings → Pages → Deploy from branch**, pick `main` (or your default branch) and `/root`. Save.
4. Your generator is now live at `https://yourusername.github.io/yourrepo/`.

## Making a new quiz

1. In Google Sheets or Excel, lay out columns: `Scramble choices?` (TRUE/FALSE), `Question`, `Answer`, then one `Choices` value per remaining column in that row. Leave the choice columns blank for a typed-answer question.
2. For the **full** format, also fill in row 1 (only) with label/value pairs after the choice columns — e.g. `Subject`, `Spanish`, `Quiz Name`, `My Quiz`, `Notes or comments`, `Some note`.
3. Select the cells, copy, and paste into the generator's textarea.
4. Pick **Simple** or **Full**, click **Generate quiz page**.
5. Click **Preview** to try it out, then **Download HTML file**.
6. Upload that file to the same repo (next to `styles.css`). Share `https://yourusername.github.io/yourrepo/filename.html` with students.

## What students see

- A **Scramble question order** toggle at the top.
- Multiple-choice or typed-answer questions, depending on whether a row has choices.
- After **Submit**, a 2-minute countdown before their score appears.
- Marked-up answers (correct/incorrect) and a score once the countdown ends.
- Scores are saved in the browser's local storage on that device, with a running history table.
- A **Clear history** button that asks for confirmation before wiping saved scores.
- Clicking **Try again** reshuffles (if scramble is on) and resets the quiz for another attempt.

## Notes and limits

- Each quiz page is fully self-contained (its questions are baked into the file) except for the shared `styles.css` link, so it works entirely as static files — no server or database needed.
- History is stored per-browser, per-device — it won't sync across a student's devices or show up for the teacher anywhere. If you need to collect scores centrally, that's a separate step (e.g. a Google Form at the end) not included here.
- The paste parser expects a simple grid (no commas/tabs embedded inside a single cell's text).
