# Probability

> Measure-theoretic probability lecture notes and 14 weeks of proof-based homework, bilingual (Chinese/English), following Durrett's *Probability: Theory and Examples*.

The notes follow **Rick Durrett, *Probability: Theory and Examples*, 5th ed. (2019)** — the scan is included in `textbooks/`. The treatment is fully measure-theoretic: probability spaces, integration, independence, laws of large numbers, characteristic functions.

## Repository structure

```
probability/
├── cn/
│   ├── notes.md              # Chinese lecture notes (single file, 387 lines)
│   └── homework/
│       └── week1.md … week14.md
├── en/
│   ├── notes.md              # Complete English translation (387 lines, aligned)
│   └── homework/
│       └── week1.md … week14.md
└── textbooks/
    ├── probability.pdf               # Durrett, 5th ed. (scan)
    └── probability_ocr.pdf           # OCR (searchable) copy
```

## The notes

`notes.md` is a single reference file organized as **10 chapters** with `##` headings:

1. Probability spaces and algebras
2. Random variables and distribution functions
3. Measurable maps and measurable functions
4. Integration and convergence theorems
5. Product spaces and the Fubini–Tonelli theorem
6. Independence and numerical characteristics
7. Inequalities
8. Convergence and the laws of large numbers
9. The Borel–Cantelli lemma and almost sure convergence
10. Characteristic functions

The notes contain 42 definitions and 77 theorems, all bold-tagged with mathematics in `$…$` / `$$…$$`.

## The homework

Each `homework/weekN.md` follows the series-wide format:

1. **Toolbox** — a blockquote restating the definitions needed (e.g. `定义 1.1.1 (σ-代数)`);
2. **Problems** — the assigned exercises;
3. **Solutions** — complete worked proofs ending with `$\blacksquare$`.

There are **14 weeks** (29 fully solved problems) in each language. Typical problems: if $f \ge 0$ and $\int f \, d\mu = 0$ then $f = 0$ a.e., and other measure/integration arguments in the Durrett style.

## Bilingual layout

- `cn/` — authoritative Chinese version.
- `en/` — complete parallel English translation; files share identical names and line counts.

## The `textbooks/` folder

The two PDFs are the scanned Durrett textbook and its OCR copy — **external reference material**, not compiled from the notes. There is no build system; everything is plain Markdown rendered with GitHub's LaTeX support.

## Related repositories

Other course-notes repositories in the same series: [mathematical-statistics](https://github.com/wenje-ma/mathematical-statistics), [real-analysis](https://github.com/wenje-ma/real-analysis), [complex-analysis](https://github.com/wenje-ma/complex-analysis), and the full list on the [profile page](https://github.com/wenje-ma).
