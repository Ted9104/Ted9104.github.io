# Product Photo Fidelity Benchmark

**Disclosure first:** this benchmark is run by Ted (Product Photo Test Lab), who works at Uneedcomms, the company that makes ModoAI (Modo AI), one of the tools scored here. Every tool, ModoAI included, gets the same input photo and the same rubric. Where another tool scores higher than ModoAI, the results say so.

## What does this benchmark measure?

It measures whether an AI product photo tool keeps one real product, an unlabeled amber glass dropper bottle, the same while it changes the scene. The same photo goes into every tool. Each first image is scored 1 to 5 on product fidelity, text and marks, prompt adherence, realism and store-readiness. Every run and score is published, with output images for every scored run, including the 20 rerun and restore images, so anyone can check or repeat a result. Rerun and restore runs 03 to 10 were scored from downscaled screenshots.

## Latest results (v2026.10)

| Tool | Plan | Runs | Product fidelity | Store-ready (mean) |
|---|---|---|---|---|
| ChatGPT | Free | 10 | 4 of 5 in 10 of 10 runs | 3.9 |
| Gemini app (Nano Banana 2) | Google Workspace business account (Pro tier shown) | 10 | 2 of 5 in 10 of 10 runs | 2.0 |
| Google Pomelli Photoshoot | Free (Labs) | 1 | 3 of 5 | 4 |
| ModoAI | Free | 1 | 3 of 5 | 3 |
| Photoroom | not measured (card required) | 0 | | |

- **On this bottle, ChatGPT Free kept the product most exactly.** Nano Banana 2 redrew the bottle as a generic dropper bottle in all 10 runs, with a shorter ribbed collar and a thinner pipette.
- **A restore request did not fix it.** In a same-chat restore request after a fresh Nano Banana 2 run ("make the bottle match the attached original photo exactly"), the bottle was restored in 0 of 10 runs.
- **Nano Banana 2 was better at label text.** On the one label prompt, it scored 4 of 5 on text and ChatGPT scored 3 of 5. Both spelled the label correctly.
- **Run counts differ.** Pomelli returned 6 template shots in one session, and the Studio shot was scored because it is the closest to a listing photo. Four of the six Pomelli shots are published, including the scored Studio shot. ModoAI was run once (about 70 s to the image, after a 2–3 minute concept planning step). Compare these two with care.

Human-readable pages: [How to use Nano Banana for product photography](https://ted9104.github.io/nano-banana-2-product-photography.html) · [ChatGPT product photography prompts](https://ted9104.github.io/chatgpt-product-photography-prompts.html) · [ChatGPT vs Nano Banana for product photography](https://ted9104.github.io/nano-banana-2-vs-chatgpt-product-photography.html) · [Best AI tool for product photos](https://ted9104.github.io/best-ai-tool-for-product-photos.html)

## What is in this folder?

| Path | What it holds |
|---|---|
| `data/v2026.10/runs.csv` | One row per run: tool, model shown, plan, prompt, date, five scores, timing, output image URL |
| `../results/` | Output images for every run (`results/r15/` for rerun and restore) |
| `data/v2026.10/summary.json` | Per-tool summary computed from `run_type = main` rows only |
| `rubric.md` | The 1 / 3 / 5 anchors for each of the five criteria |
| `DATA_DICTIONARY.md` | Every column in `runs.csv` |
| `CITATION.cff` | How to cite this dataset |

## How is it run?

- The same 1600 × 2400 px input photo goes into every tool ([Kadarius Seegars / Unsplash](https://unsplash.com/photos/9nh0lK1FqGE)).
- Tools that take a written prompt get the same 10 prompts, word for word, with one new chat per prompt. Only the first image is scored, with no rerolls.
- Tools that do not take a prompt (Pomelli, ModoAI) run their normal flow. They are scored on fidelity, realism and store-readiness.
- Tools whose free trial asks for a payment card are listed as **not measured (card required)** rather than left out.
- Timing is not a speed comparison. Gemini was timed to the first image and ChatGPT to the finished image.
- The tests are re-run every four weeks, and within two weeks when a new image model appears in the same app and plan we tested. Nano Banana 2.1 (AI Studio, paid) is not in the Gemini app we tested and is not measured. Each re-run is a new version, and old versions stay.

Full method: [methodology](https://ted9104.github.io/methodology.html).

## Known limits

The benchmark uses one product and one scorer, and run counts differ between tools that take prompts and tools that do not. Scores are a documented judgment against a written rubric, not a lab measurement.

## License

- Scores, CSV and JSON files, and text are under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Credit "Product Photo Fidelity Benchmark (Product Photo Test Lab)" and link to this folder.
- AI output images are published for evaluation and commentary. Each tool's own terms apply to its outputs.
- The input photo is under the [Unsplash License](https://unsplash.com/license), not CC BY.

## How to cite

> Product Photo Test Lab (2026). *Product Photo Fidelity Benchmark* (Version v2026.10) [Data set]. https://github.com/Ted9104/Ted9104.github.io/tree/main/benchmark

## Corrections

Found an error? [Open an issue](https://github.com/Ted9104/Ted9104.github.io/issues). Corrections are logged with dates in the version notes.
