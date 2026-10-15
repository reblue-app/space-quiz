# Copilot instructions

## Build, test, and lint

This repository is a standalone `index.html`; no package manager, build system, automated test runner, or linter is configured. Open `index.html` in a browser to run the quiz. There is no single-test command; check a specific interaction in the browser, such as answer feedback, advancing to results, or restarting.

## Architecture

The app is intentionally self-contained in `index.html`: semantic markup defines the quiz and results views, inline CSS provides responsive and light/dark styling, and inline JavaScript owns the quiz data, rendering, state, and interactions. It has no external runtime dependencies.

The `questions` array is the source for question text, choices, correct-answer indexes, and explanations. The `illustrations` array supplies the corresponding inline SVG and accessible label for each question. `showQuestion()` renders the current entries into the DOM; `chooseAnswer()` locks the answer and displays feedback; `showResults()` displays the final score; the restart handler resets state and progress.

## Repository-specific conventions

- Keep each `illustrations` entry at the same index as its `questions` entry. `correct` is a zero-based index into that question's `answers`.
- The quiz UI and result text currently assume ten questions. If changing the question count, update related fixed values in the markup and script, including progress-bar bounds, question counts, and result totals.
- Preserve the existing DOM IDs as the interface between markup and the `$()` lookup helper and rendering functions.
- Keep question/answer content as data and render text with `textContent`; answer buttons are created dynamically. SVG markup is currently authored as inline illustration literals.
- Preserve the accessibility behavior when changing interactions: feedback uses a live status region, progress exposes its current value, and focus moves to the next question or result heading at view changes.
- Keep styles and behavior in the existing inline `<style>` and `<script>` blocks unless the project is deliberately split into separate files.
