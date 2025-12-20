# scanOS – PRIOR ART DOCUMENTATION
Version: v1 (Draft)
Last updated: 2025-12-07

This document establishes **prior art** for the system known as **scanOS**,
including its method, architecture, templates, processing pipeline, and
operational scope.

scanOS is **not a program alone**, but a **method** for:

1. Ingesting arbitrary human-facing inputs  
   (including screenshots, photos, scans, documents, or text fragments).

2. Extracting information that is **visibly present** in those inputs.  
   - scanOS does not rely on hidden metadata, external databases, or prior context.
   - The method does not require or assume perfect OCR or perception.

3. Normalizing these inputs into **deterministic, machine-readable structured
   representations** (commonly JSON), following predefined templates. Other files and formats possible.

4. Applying a **template-driven structure**  
   that defines:
   - which fields exist,
   - how values are represented,
   - how uncertainties are surfaced.

5. Producing output that is suitable for **pipeline integration** with any
   downstream system, including the MetaMemoryWorks framework, analytics
   systems, automation pipelines, or third-party tools.

6. Maintaining a strict separation between:
   - **Perception** (OCR, extraction — potentially fallible)  
   - **Normalization** (deterministic, template-based)  
   - **Downstream semantics** (left to other modules or systems)

scanOS does not guarantee:
- Perfect OCR
- Perfect extraction
- Absence of misread characters
- Error-free perception

These are **perception-level limitations**, not part of the scanOS method.

What scanOS *does* define is:
- A method for structuring whatever information *can* be extracted.
- A commitment to surface uncertainties instead of silently interpreting them.
- A deterministic normalization and output layer.

---

## What scanOS *is*
- A **template-based ingestion method** for arbitrary visual/textual data.
- A **deterministic normalization layer** that transforms raw extracted content
  into structured, predictable outputs.
- A **pipeline-ready interface** for downstream modules and systems.
- A **public-good method** for individuals.

## What scanOS *is not*
- A hallucination-proof system.
- A guarantee of correct OCR.
- A prediction or reasoning engine.
- A replacement for OCR tools.
- A system that reconstructs missing or ambiguous information.

scanOS is explicitly designed to avoid **interpretive reasoning**:
it normalizes *visible* information only, but cannot fully prevent model-level
hallucination in all implementations. Any unintended inference is considered
an implementation artifact, not part of the scanOS method itself.

---

## Purpose of This Archive
This document serves to:

1. Establish **authorship and chronology** for the scanOS method.
2. Define the method in both abstract and concrete terms.
3. Prevent patent capture or monopolization of the scanOS procedure
   by third parties.
4. Clarify that scanOS is a **method**, not tied to a specific codebase.
5. Ensure that functionally equivalent systems are recognized as
   **derivative works** of this method (see license for details).

---

## Scope of Prior Art
This document constitutes prior art for the following concepts:

- Template-driven ingestion of arbitrary human-facing inputs.
- Deterministic normalization into structured data formats.
- Separation of perception (fallible) and structure (deterministic).
- Pipeline-ready output for AI and automation systems.
- A modular ingestion OS designed to sit beneath higher-level AI modules.
- A human-public-good method with controlled corporate licensing.

---

## Implementation Neutrality
scanOS may be implemented:

- in any programming language,
- with any OCR backend (cloud, local, model-based),
- with or without an LLM,
- as part of an app, CLI tool, API service, plugin, or pipeline stage.

The **method** remains the same.

Any implementation following this method, regardless of medium, constitutes
a derivative work and is covered by the corresponding license.

---

End of PRIOR_ART.md
