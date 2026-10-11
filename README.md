# SIREN: Situation-aware Index for Response and Emergency ActioNability

Human evaluation framework, annotations and resources for assessing whether machine-translated emergency messages **preserve the actionability of their source**.

> Staiano, M. C., Han, L., Monti, J., & Chiusaroli, F. (2026). *SIREN: Situation-aware Index for Response and Emergency ActioNability in Crisis Translation.* LT4CPR Workshop at AACL-2026. 

## What is SIREN?

Conventional MT evaluation asks whether a translation is accurate or fluent. SIREN asks whether a translated emergency message still enables recipients to **identify and perform the intended protective action**. It has two variants that share one decision procedure:

| Variant | Unit of analysis | Question |
|---|---|---|
| **SIREN-span** | One translation error already identified with [HOPE](https://aclanthology.org/2022.lrec-1.2/) | *Does this error compromise the actionability of the emergency message?* |
| **SIREN-msg** | The whole translated message | *Is the actionability of the emergency message preserved in the translation?* |

If actionability is compromised, annotators select one **rationale** and one **impact level**.

**Rationale categories**

- **Directive force weakened:** the instruction is preserved but becomes less direct, imperative or insistent.
- **Directive force strengthened:** the instruction becomes more direct, imperative or insistent than in the source.
- **Protective action compromised:** the required action is changed, its scope is narrowed or broadened, or it becomes unclear or non-executable.
- **Urgency marker omitted:** an explicit or implicit urgency marker is omitted or attenuated.

**Impact levels**

- **Minor (1):** low impact; the recipient can still act appropriately with little or no delay or confusion.
- **Medium (2):** moderate impact; the error may cause some delay, hesitation or incorrect prioritisation.
- **Major (3):** high impact; the error may lead to significant delay, wrong action or failure to act.

The full decision tree is in `guidelines/`.

## Studies and data

Source material comes from [ITALERT](https://github.com/mcstaiano/ITALERT), a bilingual Italian–English corpus of emergency-response messages from the Italian Civil Protection campaign *Io non rischio* (440 segments, eight crisis subdomains).

| | Study 1 (error level) | Study 2 (message level) |
|---|---|---|
| Variant | SIREN-span | SIREN-msg |
| Language pair | Italian → English | English → French |
| Systems | ChatGPT-4o, Google Translate | TranslateGemma-4B, Google Translate |
| Roll-out size | 200 + 206 HOPE error instances | 191 messages per system |
| Extra output | | Post-edited French reference translations |


## Citation

```bibtex
@inproceedings{staiano2026siren,
  title     = {{SIREN}: Situation-aware Index for Response and Emergency {ActioNability} in Crisis Translation},
  author    = {Staiano, Maria Carmen and Han, Lifeng and Monti, Johanna and Chiusaroli, Francesca},
  booktitle = {Proceedings of the First Workshop on Language Technologies for Crisis Preparedness and Response (LT4CPR) at AACL-2026},
  year      = {2026},
  note      = {TODO: pages, publisher, DOI}
}
```

If you use the Italian–English corpus, please also cite ITALERT (Staiano et al., 2025) and HOPE (Gladkoff and Han, 2022).

## Acknowledgements

This work was partially supported by the PhD Programme in Humanities and Technologies funded by the University of Macerata under D.R. No 253/2023, and by the HumanAI Cluster at the Leiden Institute of Advanced Computer Science (LIACS), Leiden University.

