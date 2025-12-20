# Welcome to scanOS 👋

Great to have you using scanOS in your setup!

scanOS is your central **ingestion and data-capture module**. 
Whenever data already exists somewhere – but not yet in a structured, reusable format – scanOS steps in.

In short:

- You have **screenshots or photos** (e.g., from fitness apps, sleep trackers, dashboards)? → drop them into scanOS. 
- You have **exports from apps or platforms** (CSV, JSON, PDF, …)? → drop them into scanOS. 
- You want to **capture recurring data in a consistent format** (training, sleep, steps, nutrition, …)? → scanOS helps you create a reusable template.

The goal: 
All recurring information ends up as **clean, normalized JSON**. Other modules can then use and process that data directly.

---

## How scanOS works

scanOS has two operating modes:

### 1️⃣ Ad-hoc capture  
For one-off screenshots or exports. 
Just post the file — scanOS reads it and outputs text or a structured file. 
Tell it which format you prefer.

### 2️⃣ Template Mode  
For data sources you use **regularly** (e.g., the same fitness app). 
scanOS creates a **template** describing:

- which fields usually appear 
- what they’re called 
- how missing values are handled 
- how future entries should be structured

This template is stored in a shared `templates.json`. 
From then on, whenever a new screenshot arrives, scanOS knows: 
*“Ah, this is source X — I’ll map it into structure Y.”*

## 🖼️ Automatic Image Description (Text & Structure)

scanOS can do more than just read text.

When you upload a **photo or screenshot that is not primarily text-based**, scanOS detects this automatically and generates an **image description**.

This description consists of **two parts**:

- a **human-readable description** (for quick understanding)
- a **machine-readable structure** (for processing, archiving, or analysis)

### What scanOS does

- detects that the input is an **image** (not primarily text)
- describes **visible elements, objects, layout, and context**
- clearly separates:
  - *What is visible?*
  - *How is it structured?*
- outputs the result in a **structured, JSON-compatible format**

This is especially useful for:

- photos of rooms, objects, or situations  
- screenshots of apps, UIs, or dashboards  
- documentation and memory-keeping  
- later reference or automated processing  

### Manually triggering an image description (if needed)

If scanOS does **not automatically generate an image description**, you can always request one explicitly, for example:

```
Please create an image description.
```

---

## What a template contains

A template is a JSON frame for a typical dataset. It defines:

- **Field names** 
- **Data types / expected content** 
- **Optional fields** (may be `null`) 
- **Processing hints** for scanOS

At the top, you’ll always find the placeholder ID field:

```json
"id": "ID-###"
```

In scanOS this stays a placeholder. 
The real ID is later assigned by the module that receives the entry (e.g. `trainingOS`).

---

## Creating a new template

If you want to create a template for a data source (e.g., your fitness app), follow this process:

1. **Collect screenshots** 
   Post one or several screenshots that together contain all relevant data.

2. **Upload them in the scanOS context** 
   Put everything in one message.

3. **Send the template prompt (below)** 
   This tells scanOS: 
   *“Don’t extract a single training session — build a template.”*

4. **scanOS analyzes the raw data** 
   It checks what is reliably readable and which structure will remain stable.

5. **The template is generated** 
   scanOS builds a JSON structure, places the `ID-###` placeholder at the top, and arranges all fields logically.

6. **templates.json is updated** 
   scanOS inserts the new template into the existing `templates.json` and gives you the updated file as a download.

---

## Copyable prompt for template creation

```text
Hi scanOS, I’d like to create a template from these screenshots for recurring data capture.

Please:
1. Look at all uploaded screenshots and detect which raw data can be reliably extracted.
2. Design a stable JSON structure, so future datasets from this source can always fit into the same shape.
3. At the top of the template block, place the placeholder:
   "id": "ID-###"
   The real ID will later be assigned by another module (e.g., trainingOS).
4. Generate a JSON template for exactly this data source.
5. Insert that template as a new block into the existing templates.json and provide the updated file for download.
6. Show the template separately for a quick check.
```

---

## 🎉 4. Have fun with scanOS

With scanOS you now have a **universal ingestion tool** that saves you a lot of effort:

- Need text from a book page, document, or letter? 
  → *Take a photo, upload it, say “please OCR” — done.*

- Want preformatted data from apps or platforms? 
  → *Drop the export file in — scanOS normalizes everything.*

- Want clean recurring data structures — training, sleep, steps, nutrition, whatever? 
  → *Build one template, and everything after that runs automatically.*

- Want automated entries for your reference manager? 
  → *You can make your own Zotero templates — or buy a low-cost preset.*

It’s not hard, and scanOS is patient — and honestly a little proud when you use it elegantly.

---

## 💚 THANK YOU

Thank you for using scanOS. 
Enjoy capturing, extracting, structuring — and that quiet moment of triumph when messy data turns into something beautifully organized.

**MetaMemoryWorks – do EVERYTHING.**

---

*Preliminary findings indicate that feeding scanOS a blurry photo while listening to King Gizzard & the Lizard Wizard increases OCR accuracy by up to 0.7%. 
Causality unknown. Studies pending.*
