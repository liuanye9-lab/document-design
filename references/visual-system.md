# Cognitive-first document design system

These are **portable design proposals**, not ChatGPT's internal CSS. They encode the principles in Lay's screenshot: constrained width, selective emphasis, whitespace grouping, special-purpose soft-gray surfaces, honest interactions, restrained colors, and different formats for different reading tasks.

## Online document tokens

| Aspect | Default | Intent |
| --- | --- | --- |
| Reading width | max 720px | Short comfortable lines |
| Gutters | 24px desktop / 16px mobile | Prevent edge-hugging |
| Body | 16px / line-height 1.75 | Mixed Chinese/English readability |
| Title | 25–29px / weight ~680 | Strong but restrained |
| H2 | 19–21px / line-height 1.45 | Main section |
| H3 | 16–17px / weight ~650 | Sub-group |
| Summary | 19px / line-height 1.6 | First-screen comprehension |
| Secondary label | 13–14px / line-height 1.6 | Support only |
| Paragraph spacing | 12–16px | Related prose |
| Section spacing | 30–36px | Cognitive topic change |
| Spacing scale | 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64px | Consistency |
| Neutral card | #F6F6F6, 1px #E8E8E8, radius 14px | Bounded facts |
| Primary / secondary ink | #171717 / #686868 | Low visual noise |
| Interactive hit area | ≥44px | When HTML form is meaningful |

Normal explanation stays on white. Avoid gray backgrounds behind full pages, nested cards, uniform bolding, excess title levels, decorative color, or fake controls. Allow table-local horizontal scrolling on mobile while keeping the main page within the viewport.

## Formal print tokens

| Aspect | Default | Why |
| --- | --- | --- |
| Paper | Letter portrait by default; A4 when specified | Honor user/institution requirements |
| Margins | 0.95–1.0in (~24–25mm) | Balanced page |
| Document title | 22–24pt black bold | Subject clear without underline/rule |
| H1 | 15–16pt black semibold | Section orientation |
| H2 | 12–13pt black semibold | Subsection |
| Body | 11pt, ~1.45 line spacing | Sustained print reading |
| Summary | 11.5pt, selective strong phrase | Opening insight |
| Paragraph after | ~6pt | Comfortable flow |
| H1 before / after | ~16pt / 7pt | Grouping |
| Tables | Light-gray 0.5pt borders, deliberate widths, cell padding | Exact comparison |
| Pagination | Keep heading with next, avoid split rows, inspect widows | No orphaned content |

**A print document is not a web UI.** Replace a web gray note card with a bold lead-in paragraph in Word; only use shaded table cells for actual labels/comparison fields. No decorative horizontal title rules or boxes surrounding paragraphs.

## Semantic routing

- `paragraph` explains relationships, constraints, recommendations or evidence.
- `facts` groups 2–5 succinct labels and values.
- `steps` lists ordered dependencies; each step names a distinct action.
- `list` names separable items without an implied sequence.
- `table` displays comparable records or metrics; never use it to squeeze narrative into columns.
- `note` is rare bounded side information; online muted block, formal bold introductory sentence.
- `choice` is optional, only when selecting an answer changes tailored feedback. In Word/PDF it is a **static** questionnaire.

## First-five-seconds check

The title names the subject, the summary says what matters, major headings can be understood alone, risks are not hidden, and the first screen/page is not overwhelmed by decorative UI.
