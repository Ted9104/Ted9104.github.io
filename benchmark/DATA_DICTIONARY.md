# Data dictionary: runs.csv

One row per run. Columns follow the fields already recorded on the methodology page (https://ted9104.github.io/methodology.html).

| Column | Type | Meaning |
|---|---|---|
| version | text | Benchmark version, e.g. `v2026.10` |
| run_id | text | Page and prompt, e.g. `l1-03` (Nano Banana 2, prompt 3), `l2-08` (ChatGPT, prompt 8) |
| run_type | text | `main` = scored first image. `main_rerun` = the same prompt run again in a new chat on 2026-10-30, first image. `e1_restore` = same-chat restore request after that rerun. Summaries use `main` only |
| tool | text | Tool name as sold, e.g. `ChatGPT`, `Gemini app (Nano Banana 2)`, `Google Pomelli Photoshoot`, `ModoAI` |
| model_shown | text | Model name the app displayed on the image screen, or `not shown` |
| plan | text | Plan name as shown in the app, e.g. `ChatGPT Free`, `Free (Labs)`, `Google Workspace business account (Gemini app, Pro tier shown)` |
| run_date | date | YYYY-MM-DD, KST |
| prompt_id | text | `p01`–`p10`, or `none` for tools that take no prompt |
| input_flow | text | `prompt` or `tool_flow` (the tool's own steps, e.g. recommended style) |
| time_to_image_s | number | Seconds from send to the first image (Gemini) or finished image (ChatGPT). Empty if untimed |
| fidelity | 1–5 | Product fidelity |
| text_marks | 1–5 | Text and marks. Empty for tool_flow runs |
| prompt_adherence | 1–5 | Empty for tool_flow runs |
| realism | 1–5 | |
| store_ready | 1–5 | |
| total | number | Sum of the scores present |
| shape_preserved | text | `Yes`, `Partly` or `No`, optionally followed by `: detail` |
| invented_text_or_logo | text | `Yes` or `No`, optionally with a short note in brackets, e.g. `No (only the requested label)` |
| color_true | text | `Yes`, `Partly` or `No`, optionally followed by `: detail` |
| output_size_px | text | Size of the image the app returned, e.g. `1024 x 1536`. Published files for r15-03 to r15-10 are smaller screenshots |
| watermark_visible | text | `Yes` or `No`; empty if not recorded |
| image_path | text | URL of the published output image (rerun and restore images are under `results/r15/`) |
| status | text | `measured`, or `not measured (card required)`, `not measured (unavailable in region)` |
| notes | text | Scorer's one-sentence verdict or run note; for `e1_restore` rows, `restored: Yes/No` |

## summary.json

Per tool, computed from `run_type = main` and `status = measured` rows: `runs`, `fidelity_mode`, `fidelity_mean`, `fidelity_min`, `fidelity_max`, `realism_mean`, `store_ready_mean`, `time_to_image_s_range`, and `e1_restore` (`restored / attempts`) where E1 was run. Tools with no measured rows appear with `status` only. Top level: `generated`, `source`, `license`, `caveats`. Per tool: `criteria_scored` (5 or 3), and where relevant `time_note` or `selection_note`.
