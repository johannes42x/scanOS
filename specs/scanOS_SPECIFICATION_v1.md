# scanOS – Method Specification (v1)
Version: 1.0  
Status: Stable Draft  
Last Updated: 2025-12-07  

## 0. Purpose and Scope
scanOS defines a **method** for converting arbitrary human-facing inputs  
(e.g. screenshots, photos, scans, documents, or text fragments) into  
**deterministic, machine-readable structured representations** using  
predefined templates.

scanOS is not a model and not tied to any specific software implementation.  
It describes a **procedure**, not a program.  
scanOS may also be distributed as a **commercial product** implementing this method,
but its identity is defined by the method itself, not by any particular codebase.

The method ensures:
- Predictable structure  
- Template conformity  
- Deterministic normalization  
- Transparently surfaced uncertainties  
- Pipeline-ready output for downstream systems  

The method does **not** guarantee perfect perception or absence of model errors.

---

## 1. Inputs
scanOS accepts arbitrary visible or textual inputs, including:

- Screenshots  
- Photos (camera-captured content)  
- Scans  
- Mixed-content documents  
- Text fragments  

Inputs may contain:
- noise, distortion, blur  
- partial content  
- incomplete sections  
- multiple text regions  
- mixed languages  

The method requires that implementations operate **extraction-first**, not inference-first.

---

## 2. Processing Pipeline Overview
scanOS defines a four-stage processing pipeline.  
Implementations may vary, but all must preserve the method’s conceptual structure.

### 2.1 Stage 1 — Extraction
Purpose: Pull visible information from the input.

Rules:
- Extract what is *visibly present*.  
- Use OCR or equivalent techniques where necessary.  
- Surface unreadable or unclear regions.  
- Do not intentionally fabricate missing content.  
- Do not rely on hidden metadata or external context.  

Extraction errors (e.g., OCR mistakes) are **expected** and do not violate the method.

For non-text-dominant inputs, extraction may produce structured
descriptive representations of visible elements instead of OCR text.

---

### 2.2 Stage 2 — Template Selection
Each ingestion task uses a predefined template, e.g.:

- sleep data  
- nutrition labels  
- receipts and invoices  
- training logs  
- general note structures  

Rules:
- Choose an appropriate template.  
- Validate mandatory fields.  
- Allow nulls where data is missing or unreadable.  
- No template may require data the input does not provide.  

Templates are format-agnostic and may evolve over time.

**Changing field names or output schemas does not remove a system from being a scanOS implementation if the underlying method is followed.**

---

### 2.3 Stage 3 — Normalization
Purpose: Transform extracted data into deterministic structured output.

Normalization includes:
- converting units  
- parsing numeric values  
- mapping fields to template keys  
- applying consistent formatting rules  

Normalization must follow **mechanical, deterministic rules**, not semantic inference.

Examples:
- "67 BPM" → `67`  
- "1 Std. 8 Min." → `1.13` hours  
- "kcal/100g" → numeric fields  

Allowed:
- standardizing formats  
- converting units  
- surfacing uncertainties (`null`, `"unreadable"`)

Not allowed:
- semantic reconstruction  
- domain reasoning ("this is probably…")  
- estimating missing values  

---

### 2.4 Stage 4 — Output Generation
Outputs must:

- follow the selected template  
- be deterministic  
- include all extracted values  
- allow null fields  
- include uncertainty markers  
- record source-file names if provided  

Formats:
- JSON (common default)  
- YAML, XML, CSV, or other structured formats  
  → **Format does not change the identity of the method.**

---

## 3. Error Model
scanOS distinguishes between two issue categories:

### 3.1 Perception-Level Errors  
(e.g., OCR mistakes, unreadable regions, missing text)

Expected, normal, allowed.  
Implementations must surface these transparently.

### 3.2 Implementation Artifacts  
(e.g., hallucinated values, unintended semantic guesses)

These may occur depending on the chosen tools (e.g., LLMs),  
but they are **not part of the scanOS method**.

The method requires:
- minimizing unintended inference,  
- never intentionally adding unseen data,  
- surfacing ambiguity rather than resolving it silently.

---

## 4. Template System
Templates define:

- field names  
- data types  
- required vs optional fields  
- allowed nullability  
- unit conventions  
- expected output structure  

Templates are part of the scanOS method and are considered derivative works.

A template is valid if:
- it is deterministic  
- it contains no required fields that cannot be obtained from visible input  
- normalization rules can be applied mechanically  

**Changing field names, output formats, or storage media does not remove a system
from being a scanOS implementation if the underlying method is followed.**

---

## 5. Pipeline Integration
scanOS outputs are designed for seamless integration with any downstream system, including but not limited to:

- the MetaMemoryWorks framework  
- data analytics pipelines  
- automation workflows  
- third-party processing tools  
- archival or research workflows  

scanOS may appear at the **beginning, middle, or end** of a pipeline.

The method is compatible with:
- batch processing  
- real-time ingestion  
- interactive workflows  
- automated ETL systems  

---

## 6. Implementation Neutrality
scanOS is a **method**, not tied to any:

- programming language  
- runtime  
- operating system  
- OCR engine  
- AI model  
- UI or API  
- storage format  

Any implementation that follows the method — regardless of technical substrate — qualifies as scanOS.

Media-shift (e.g. image → text → JSON), format-shift (e.g. JSON → YAML), and implementation-shift (e.g. local → cloud → LLM) do **not** change the identity of the method.

---

## 7. Versioning
scanOS uses semantic versioning for the specification:

- **MAJOR** — breaking conceptual or methodological changes  
- **MINOR** — new templates or structural extensions  
- **PATCH** — clarifications or refinements  

Templates MAY version independently.

---

## 8. Out of Scope
scanOS does not define:

- how OCR must be implemented  
- how LLMs handle perception  
- how errors should be corrected  
- user interface behavior  
- storage systems  
- SDKs or APIs  

scanOS is the **ingestion and normalization method only**.

---

## 9. Summary
scanOS v1 defines:

- a structured ingestion method  
- deterministic normalization  
- template-based structuring  
- transparent handling of uncertainty  
- pipeline-ready output  
- full implementation neutrality  

It is a foundational component of the MetaMemoryWorks ecosystem,  
but also a standalone, general-purpose ingestion method for arbitrary AI
and automation pipelines.
