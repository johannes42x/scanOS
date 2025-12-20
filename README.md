# scanOS
A template-driven ingestion and normalization method for converting arbitrary
human-facing inputs into deterministic, machine-readable structured data.

Version: 1.0  
Status: Stable Draft  

---

## What is scanOS?
scanOS is a **method and product** for transforming screenshots, photos, scans,
documents, or text fragments into structured representations using predefined
templates and deterministic normalization rules.

It provides a consistent, predictable way to extract visible information and
convert it into formats suitable for downstream processing, analytics, and
automation workflows.

scanOS is **implementation-neutral**:  
it is not tied to any specific programming language, OCR engine, runtime,
or AI model. Any system that follows the method is considered an implementation
of scanOS.

---

## Key Features
- Template-driven ingestion  
- Deterministic normalization rules  
- Transparent handling of uncertainty  
- Structured output (JSON, YAML, XML, CSV, etc.)  
- Compatible with batch, real-time, and interactive workflows  
- Designed for pipeline integration with any downstream system  
  (including MetaMemoryWorks modules such as trainingOS, nutritionOS, sleepOS)

---

## What scanOS is **not**
- Not an OCR model  
- Not a hallucination-proof system  
- Not a prediction or reasoning engine  
- Not guaranteed to extract data perfectly  
- Not tied to a single implementation or technology stack  

scanOS defines **how** ingestion and normalization must be performed, not the
specific tools used to perform it.

---

## Method Specification
The full technical description of the scanOS method is available in:

→ [`scanOS_SPECIFICATION_v1.md`](scanOS_SPECIFICATION_v1.md)

This document defines:
- inputs  
- processing pipeline  
- template system  
- normalization rules  
- error model  
- implementation neutrality  

---

## License
scanOS is free for **individual, non-commercial use**.

Corporate, institutional, or governmental use requires a **commercial license**.

The full licensing terms are defined in:

→ [`scanOS_RESTRICTED_LICENSE_v1.0.md`](scanOS_RESTRICTED_LICENSE_v1.0.md)

The license also defines:
- derivative works  
- restrictions on commercial use  
- prohibitions  
- warranty disclaimer  

---

## Prior Art
The method, structure, and conceptual origins of scanOS are documented in:

→ [`scanOS_PRIOR_ART.md`](scanOS_PRIOR_ART.md)

This establishes authorship, chronology, and prevents patent capture.

---

## Implementation Neutrality
scanOS may be implemented:

- in any programming language  
- with any OCR backend  
- with or without language models  
- on local or cloud systems  
- in CLI tools, APIs, or applications  

Format-shifting, media-shifting, or implementation-shifting does not remove
a system from being considered an implementation of scanOS if the method is
followed.

---

## Versioning
scanOS uses semantic versioning for the specification.  
Templates may version independently.

---

## Contact
For licensing inquiries or questions regarding commercial use, please contact:

**Johannes Glaser**  
(Author and Copyright Holder)
