# 🏗️ Alysa - Construction Intelligence MVP

Alysa är ett AI-drivet verktyg för att automatisera analysen av förfrågningsunderlag (LOU/LUF, AB04, ABT06, ABK09). Systemet hjälper anbudsingenjörer att snabbt identifiera skall-krav och kontraktuella risker.

![Alysa Screenshot](https://via.placeholder.com/800x400?text=Alysa+Interface+Placeholder)

## 🚀 Funktioner

- **AI-Analys:** Drivs av Google Gemini 1.5 Flash för snabb och kostnadseffektiv analys.
- **Kravhantering:** Identifierar och klassificerar automatiskt "SKALL"-krav vs "BÖR"-krav.
- **Riskanalys:** Varnar för avvikelser i viten, garantitider och ansvarsbegränsningar.
- **Smart Sökning:** Klicka på ett krav för att direkt hoppa till textstycket i originaldokumentet (fungerar även för PDF/DOCX).
- **Formatstöd:** Hanterar PDF, DOCX, XLSX och ZIP-filer.
- **Chatt-assistent:** Ställ följdfrågor till underlaget direkt i gränssnittet.

## 🛠️ Tech Stack

- **Backend:** Python (FastAPI)
- **AI Engine:** Google Gemini API (via `google-generativeai`)
- **Frontend:** HTML5, Tailwind CSS, JavaScript (Vanilla)
- **Dokumenthantering:** PyMuPDF (PDF), python-docx (Word)

## 📦 Installation & Körning

För att köra projektet lokalt:

1. **Klona repot:**
   ```bash
   git clone [https://github.com/oscoro123/Alysa_mvp.git](https://github.com/oscoro123/Alysa_mvp.git)
   cd Alysa_mvp