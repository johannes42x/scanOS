# scanOS

scanOS defines how visible information becomes structured data that persists.

Screenshots, photos, scans, documents, and other human-facing artifacts contain
information that is usually read once, summarized, and discarded.
scanOS specifies a **repeatable ingestion and normalization method** that turns
what is visible into deterministic, machine-readable files.

scanOS is designed for situations where information must not only be recognized,
but **retained, compared, and reused over time**.

---

This repository is part of **MetaMemoryWorks** —  
a file-based architecture for persistent AI memory.

🌐 https://metamemoryworks.com  
📄 Architecture: https://github.com/johannes42x/MetaMemoryArchitecture

Version: 0.9.0

---

## What is scanOS?

scanOS is a **method and product** for transforming screenshots, photos, scans,
documents, or text fragments into structured representations using predefined
templates and deterministic normalization rules.

It provides a consistent, predictable way to extract visible information and
convert it into formats suitable for downstream processing, analytics, and
automation workflows.

scanOS is **implementation-neutral**:

- it is not tied to any specific programming language  
- not bound to a particular OCR engine  
- not dependent on a specific runtime or AI model  

Any system that follows the scanOS method is considered a valid implementation.

---

## What problem scanOS addresses

Most visual ingestion tools focus on *recognition*:
you upload an image, receive text or annotations, and move on.

scanOS focuses on **stability**:

- repeated inputs of the same type produce comparable outputs  
- structure is explicit, inspectable, and file-based  
- outputs are designed to persist, not disappear in chats or UIs  

scanOS is intended as an ingestion layer wherever visual information must become
part of a longer-lived data flow or memory system.

---

## Core characteristics

- Template-driven ingestion  
- Deterministic normalization rules  
- Explicit handling of uncertainty and ambiguity  
- Structured outputs (JSON, YAML, XML, CSV, etc.)  
- Compatible with batch, real-time, and interactive workflows  
- Designed for pipeline integration with any downstream system  
  (including MetaMemoryWorks modules such as trainingOS, nutritionOS, sleepOS)

---

## What scanOS is **not**

scanOS intentionally does **not** claim properties it cannot guarantee:

- Not an OCR model  
- Not hallucination-proof  
- Not a prediction or reasoning engine  
- Not guaranteed to extract data perfectly  
- Not tied to a single implementation or technology stack  

scanOS defines **how ingestion and normalization must be performed**,  
not which tools must be used to perform them.

---

## Implementation neutrality

scanOS may be implemented:

- in any programming language  
- with any OCR backend  
- with or without language models  
- on local or cloud systems  
- as CLI tools, APIs, services, or embedded components  

Changing format, medium, or execution environment does not remove a system from
being considered a scanOS implementation, as long as the method is followed.

---

## Relation to MetaMemoryWorks

scanOS can be used standalone.

Within MetaMemoryWorks, it typically serves as:

- the ingestion layer for visually sourced information  
- a normalization bridge between human-facing artifacts and file-based memory  
- an upstream component for modules such as trainingOS, nutritionOS, sleepOS  

scanOS does not require the MetaMemoryWorks stack, but integrates cleanly with it.

---

## Versioning

scanOS uses semantic versioning for the specification.

Templates, rulesets, and presets may version independently.

---

## Licensing

- Private, non-commercial use: free  
- Commercial or institutional use: license required  

See the license files in `/legal/` for details.

For licensing inquiries:
lizenz@metamemoryworks.de  
licensing@metamemoryworks.com

For everything else:
kontakt@metamemoryworks.de  
contact@metamemoryworks.com
