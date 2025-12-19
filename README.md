🏗️ Alysa - Construction Intelligence MVP
Alysa is an AI-powered analysis tool designed for the construction industry. It automates the review of Request for Proposals (Förfrågningsunderlag) by extracting critical requirements ("SKALL-krav"), preferences ("BÖR-krav"), and potential risks from complex documentation.

Add a real screenshot here later

🌟 Key Features
Multi-Format Support: Analyzes PDF, DOCX, and ZIP archives containing multiple files.

AI-Powered Analysis: Uses Google Gemini 1.5 Flash to intelligently extract and classify requirements.

Deep-Link Referencing (The "Killer Feature"):

Clicking a requirement card instantly scrolls to the exact source text in the document.

PDF: Uses a smart coordinate-based overlay system with fuzzy search to handle fragmented PDF text layers.

DOCX: Uses robust DOM-based highlighting that handles line breaks and formatting changes.

Intelligent Navigation:

ZIP files generate a clickable header menu to jump between different documents within the analysis view.

Risk Assessment: Identifies financial and legal risks (viten, betalningsplaner, etc.).

Chat Assistant: Integrated AI chat to ask follow-up questions about the specific documents loaded.

🛠️ Tech Stack
Backend: Python 3.9+, FastAPI, Uvicorn.

AI Engine: Google Generative AI (Gemini via API).

Frontend: Vanilla HTML5, JavaScript (ES6+), Tailwind CSS (via CDN).

Document Processing:

PyMuPDF (Fitz) for PDF text extraction.

python-docx for Word documents.

pdf.js for rendering PDFs in the browser.

🚀 Installation & Setup
1. Clone the repository
Bash
git clone https://github.com/oscoro123/Alysa_mvp.git
cd Alysa_mvp
2. Create a Virtual Environment
Bash
# Mac/Linux
python3 -m venv venv
source venv/bin/activate

# Windows
python -m venv venv
.\venv\Scripts\activate
3. Install Dependencies
Bash
pip install -r requirements.txt
(If requirements.txt is missing, install manually: pip install fastapi uvicorn python-multipart google-generativeai pymupdf python-docx)

4. Configure Environment
Create a .env file in the root directory and add your Google Gemini API key:

Kodavsnitt
GOOGLE_API_KEY=Din_Hemliga_Nyckel_Här
5. Run the Server
Bash
uvicorn api:app --reload
The application will start at http://127.0.0.1:8000.

📂 Project Structure
api.py: The FastAPI backend. Handles file uploads, text cleaning (clean_text), and routes traffic.

extractor.py: Contains the logic for communicating with Google Gemini and parsing the JSON response.

index.html: The complete Frontend. Contains the logic for:

PDF Rendering (pdf.js).

Text Rendering (DOCX/ZIP).

The Highlighter Engines: Contains the specific algorithms (highlightPDF and highlightDOCX) for drawing yellow overlays on the correct text segments.

system_prompt.txt: The instructions given to the AI (Anbudsingenjör persona).

🤝 Integration Notes (For Gustav / Web Team)
If merging this MVP into a larger website (e.g., Next.js, React, or another platform), note the following:

Backend Separation: The api.py is a standalone microservice. It exposes:

POST /analyze: Expects a file (multipart/form-data). Returns JSON with summary, requirements, risks, and extracted_text_view.

POST /chat: Expects JSON {"question": "..."}.

Frontend Logic: The highlighting logic in index.html is critical.

Do not rely on exact string matching. The current implementation uses a "fuzzy sequence matching" algorithm because PDF text layers are often fragmented.

PDFs: Must be rendered using a canvas-based library (like pdf.js) where we can overlay divs based on coordinates.

DOCX: Rendered as HTML text. We use window.find with aggressive string cleaning to locate the text nodes.

🔮 Future Roadmap
[ ] User Accounts & Project History (Database integration).

[ ] "Pay-as-you-go" API billing integration.

[ ] Export analysis to Excel/PDF.

[ ] Multi-file upload (drag and drop multiple distinct files).

Built for the future of construction tenders.
