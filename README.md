# Any Topic Q&A Generator - Universal Assessment Studio

**Any Topic Q&A Generator** (OmniAssess AI) is an interactive, universal single-file web application built with **HTML5, Tailwind CSS, and vanilla JavaScript**, configured strictly to use Google's **`gemini-3.8-flash`** model. Generate instant, comprehensive question papers and step-by-step solutions for any topic, subject, or exam.

---

## 🌟 Key Features

### 1. Unified Step-by-Step Control Panel in Warm Academic Cream (`#FDFBD6`)
A single, cohesive, card-based panel right at the top styled in clean cream (`#FDFBD6`) with high-contrast dark slate/charcoal typography (`#1e293b` / `#0f172a`):
- **Step 1: Enter Any Topic**: Enter any chapter, topic, semester, or concept directly. Includes search icon, clear button, and keyboard `Enter` listener for rapid generation without extra menus.
- **Step 2: Choose Discipline / Field**: Includes built-in disciplines, quick interactive pills, and an inline **Add Custom Subject** form with delete (`x`) capability persisted in `localStorage`.
- **Step 3: Select Target Standard / Level**: Select from organized `<optgroup>`s covering Engineering Semesters 1–8, School Boards (Class 9–12), Competitive Exams (JEE, NEET, GATE, CAT, UPSC), Professional Tech Certifications (AWS, LeetCode, PMP, CFA), and University degrees.
- **Step 4: Select Difficulty Level**: Choose from *Foundational / Beginner, Moderate, Balanced (Recommended), Challenging / HOTS, Extreme / Olympiad / GATE*.
- **Optional Format & Blueprint Drawer**: Toggleable advanced settings for Exam Mode Architecture (Academic vs. Competitive), Exam Duration, and Category Distribution Sliders with live question and marks tallies.

### 2. Clean, Uncluttered Workflow (Presets Menu Removed)
- Redundant preset menus and drawers have been removed from the header to keep the interface strictly focused on the sequential 4-step workflow.

### 3. Single Glowing Primary Action Button
- One prominent, glowing **"Generate Q&A"** button at the conclusion of the unified control panel.
- Instantly gathers all selections from Steps 1–4, disables UI into a tactile spinner state, smoothly scrolls down to the live 4-step loading indicator, and upon completion with Gemini 3.8 Flash, smoothly scrolls directly to the generated question paper.

### 4. High-Contrast Paper & Question Cards (`#FDFBD6`)
- Examination paper container (`#testPaperContainer`), question cards, and solution drawers all rendered in the clean cream color (`#FDFBD6`) with dark charcoal text for clarity and readability.

### 6. Dynamic Dual-Mode Architecture
- **Mode A: Academic / University / Board Mode:** Objective MCQs (1M), Very Short Answer VSA (2M), Short Answer SA (3M), Long Answer LA (5/10M), and Case/Competency studies with step-by-step point rubrics.
- **Mode B: Competitive / Entrance / Professional Exam Mode:** Single Correct MCQs (+4, -1), Multiple Correct MCQs (with partial scoring), Numerical / Integer Value Type, Assertion-Reasoning, Matrix Match Columns, and Paragraph Comprehension.

### 7. Fresh, Non-Cached Randomization Engine
- Injects a high-entropy variation nonce, random seed (`#100000 - #999999`), and ISO timestamp directly into the prompt payload on every request.
- Strict system prompt directives forcing Gemini 3.8 Flash to formulate brand-new numerical figures, problem contexts, real-world scenarios, and distractor sets.
- Dedicated **"🎲 Fresh Re-roll"** action to generate a completely distinct assessment for the current topic with one click.

### 8. Robust Technical Stack & Fallbacks
- Configured strictly to:
  ```
  https://generativelanguage.googleapis.com/v1beta/models/gemini-3.8-flash:generateContent?key=${apiKey}
  ```
  with standard `Content-Type: application/json` and `responseMimeType: "application/json"`.
- **Timeout Protection:** 35-second `AbortController` timeout guard with live elapsed second counter.
- **Enhanced Offline Mock Generator:** Comprehensive offline syllabus generator covering Engineering Semesters, Board Exams, Competitive Exams, and custom procedural synthesis.

### 9. Section Filters, Practice Mode & Export Suite
- **Section Filter Tabs:** Switch between "All Sections", "Sec A", "Sec B", "Sec C", etc.
- **Interactive Practice Mode:** Clickable MCQ choices and numerical input verification with instant feedback.
- **Teacher Marking Mode:** Full step-by-step point-by-point marking schemes and pedagogical takeaways.
- **Master Solution Toggle:** Instant expand/collapse for all question rubrics.
- **Export Suite:**
  - "Export as Markdown (.md)" download.
  - "Print / Save as PDF" via clean `@media print` styling without website buttons or clutter.
  - "Copy to Clipboard" with toast confirmation.

---

## 🚀 How to Run

1. Open [`index.html`](file:///C:/Users/USER/.gemini/antigravity/scratch/universal-qa-generator/index.html) directly in any modern web browser.
2. Or start a local static server:
   ```powershell
   python -m http.server 8000 --directory C:\Users\USER\.gemini\antigravity\scratch\universal-qa-generator
   ```
3. Set [`C:\Users\USER\.gemini\antigravity\scratch\universal-qa-generator`](file:///C:/Users/USER/.gemini/antigravity/scratch/universal-qa-generator) as your active workspace for future work.

---

## 🚀 How to Run

1. Open [`index.html`](file:///C:/Users/USER/.gemini/antigravity/scratch/universal-qa-generator/index.html) directly in any modern web browser.
2. Or start a local static server:
   ```powershell
   python -m http.server 8000 --directory C:\Users\USER\.gemini\antigravity\scratch\universal-qa-generator
   ```
3. Set [`C:\Users\USER\.gemini\antigravity\scratch\universal-qa-generator`](file:///C:/Users/USER/.gemini/antigravity/scratch/universal-qa-generator) as your active workspace for future work.
