# Unit 11: Development Individual Project (presentation)

**Learning outcomes:** LO1, LO2, LO3 · **Submitted:** 11 October 2026

**Question:** *Can a model read the word class off a Bliss symbol?* Blissymbolics is a symbol language used by
some non-speaking people. Each symbol is colour coded by word class: things, actions, people or descriptions.
I trained models to predict that class from the drawing alone.

## Files here

| File | What it is |
|---|---|
| [bliss_wordclass_executed.ipynb](bliss_wordclass_executed.ipynb) | The full executed notebook |
| [bliss_wordclass_executed.pdf](bliss_wordclass_executed.pdf) | The same notebook as a PDF |
| [Bliss_wordclass_presentation.pptx](Bliss_wordclass_presentation.pptx) | The slides |
| [Bliss_wordclass_transcript_outline.docx](Bliss_wordclass_transcript_outline.docx) | The transcript outline for the recorded talk |
| [evaluation_vs_unit06.md](evaluation_vs_unit06.md) | My evaluation of this project against the Unit 6 team project |

## In short

- **Data:** the official BCI-AV release from Blissymbolics Communication International (CC BY-SA 4.0). 6,015
  symbols in 4 content-word classes.
- **Models:** HOG features + SVM (classical), a small CNN, and a pretrained ResNet18, plus several pre-declared
  variants.
- **Validation:** I held out a test set first and touched it once at the end. Model comparison used stratified
  5-fold cross-validation, with related symbols kept together so a model couldn't score by recognising shared
  parts.
- **Result:** the best deep model (ResNet18) and the best classical model (HOG + SVM, left-aligned) finished
  level on the held-out test set: macro F1 0.936 vs 0.945, p = 0.56.
- **The biggest single gain came from understanding Bliss, not from a bigger model.** Left-aligning the drawings,
  because the first character sets the category, added 0.032 to the SVM.
- **Explainability:** LIME and Grad-CAM show the models use the same small mark a person would use to tell an
  action from a description.
