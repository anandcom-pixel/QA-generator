# Any Topic Q&A Generator - Universal Assessment Studio

**Any Topic Q&A Generator** (OmniAssess AI) is an interactive, universal single-file web application built with **HTML5, Tailwind CSS, and vanilla JavaScript**, configured strictly to use Google's **`gemini-3.8-flash`** model. Generate instant, comprehensive question papers and step-by-step solutions for any topic, subject, or exam.

---

## 🌟 Key Features

### 1. Unified Step-by-Step Control Panel in Warm Academic Cream (`#FDFBD6`)
A single, cohesive, card-based panel right at the top styled in clean cream (`#FDFBD6`) with high-contrast dark slate/charcoal typography (`#1e293b` / `#0f172a`):
- **Step 1: Enter Any Topic**: Enter any chapter, topic, semester, or concept directly. Includes search icon, clear button, and keyboard `Enter` listener for rapid generation without extra menus.
- **Step 2: Choose Discipline / Field**: Includes built-in disciplines, quick interactive pills, and an inline **Add Custom Subject** form with delete (`x`) capability persisted in `localStorage`.
- **Exam Architecture Format Cards**: Prominent dual cards positioned directly above target level & difficulty:
  - **Option 1: School / Board Exam Mode** (CBSE, ICSE / ISC, State Boards, University / B.Tech) with structured step rubrics (1M, 2M, 3M, 5M, Case passages) and no negative penalties.
  - **Option 2: Competitive / Entrance Exam Mode** (JEE Main & Adv, NEET-UG, GATE, CAT / MBA, UPSC / Certs) with negative marking (+4, -1), multiple correct, numerical, and matrix match formats.
- **Step 3: Select Target Standard / Level**: Select from organized `<optgroup>`s covering Engineering Semesters 1–8, School Boards (Class 9–12), Competitive Exams (JEE, NEET, GATE, CAT, UPSC), Professional Tech Certifications (AWS, LeetCode, PMP, CFA), and University degrees.
- **Step 4: Select Difficulty Level**: Choose from *Foundational / Beginner, Moderate, Balanced (Recommended), Challenging / HOTS, Extreme / Olympiad / GATE*.
- **Question Category Distribution Blueprint (20–25 Questions Full Assessment)**:
  - Complete fine-tuning grid for both exam modes with live interactive range sliders and increment/decrement (`+` / `-`) buttons.
  - Defaults to **24 questions total** (e.g., 10 MCQs, 5 VSA, 4 SA, 3 LA, 2 Case/Numerical for Board Mode; 10 Single Correct, 4 Multiple Correct, 4 Numerical, 3 Assertion-Reason, 2 Matrix Match, 1 Passage for Competitive Mode).
  - Real-time tally badges dynamically updating total questions and maximum marks.
  - Strict system prompt payload synchronization passing exact section breakdown and question volumes to active AI models.

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

### 5. Multi-Model AI Routing (Google Gemini & Groq Cloud)
- **Footer Model Switcher**: Seamlessly switch between:
  - **Google Gemini 3.8 Flash** (`gemini-3.8-flash`) — Google's high-speed multimodal reasoning model.
  - **Groq Qwen 3.8 27B** (`qwen/qwen3.8-27b`) — Ultra-low-latency Groq LPU inference.
- **Dynamic API Routing**:
  - Gemini queries dispatch to `https://generativelanguage.googleapis.com/v1beta/models/gemini-3.8-flash:generateContent?key=${apiKey}` with native JSON mode.
  - Groq queries dispatch to `https://api.groq.com/openai/v1/chat/completions` with Bearer auth, model string `qwen/qwen3.8-27b`, and `response_format: {"type": "json_object"}`.
- **Provider-Aware Key Management**:
  - Automatically prompts users for their Groq key when switching to Groq if no key is stored.
  - Stored strictly in browser `localStorage` (`omniassess_gemini_api_key` and `omniassess_groq_api_key`) and model choice persisted across sessions.
  - Quick links to both [Google AI Studio](https://aistudio.google.com/app/apikey) and [Groq Console](https://console.groq.com/keys).

---

## 🚀 How to Run

1. Open [`index.html`](file:///C:/Users/USER/.gemini/antigravity/scratch/universal-qa-generator/index.html) directly in any modern web browser.
2. Or start a local static server:
   ```powershell
   python -m http.server 8000 --directory C:\Users\USER\.gemini\antigravity\scratch\universal-qa-generator
   ```
3. Set [`C:\Users\USER\.gemini\antigravity\scratch\universal-qa-generator`](file:///C:/Users/USER/.gemini/antigravity/scratch/universal-qa-generator) as your active workspace for future work.
