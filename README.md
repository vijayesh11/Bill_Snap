BillSnap

AI-powered PWA that scans bills and receipts, extracts merchant, date, amount, and category using OCR and Groq AI, and shows spending analytics.

Overview

BillSnap is a Progressive Web App (PWA) that uses Tesseract.js for on-device OCR (with adaptive thresholding and multi-PSM handwriting support) and Groq AI for intelligent field extraction — detecting merchant name, date, total amount, and expense category from any bill photo, including handwritten, printed, blurry, or angled receipts.

Features
Scan any bill — printed, handwritten, blurry, or angled
Groq AI extracts merchant, date, amount, and category
Handwriting support via adaptive thresholding and multi-PSM OCR
Handles Indian GST bills, cash memos, and international receipts
Confidence badges — VERIFIED / REVIEW / UNCERTAIN per field
Manually edit any extracted field before saving
Spending analytics dashboard with charts
All data stored locally (IndexedDB — no server needed)
Installable as a PWA on mobile and desktop
Tech Stack
Layer	Technology
Frontend	React + Vite + TypeScript
Styling	Tailwind CSS v4
OCR	Tesseract.js 5 (multi-PSM: 4, 6, 11)
AI Extraction	Groq API (openai/gpt-oss-120b)
Storage	Dexie (IndexedDB)
Charts	Recharts
PWA	vite-plugin-pwa
Getting Started
bash
cd frontend
npm install
npm run dev

Then open http://localhost:5173

How It Works
Upload or capture a bill photo
Image is preprocessed (adaptive thresholding, sharpening, upscaling)
Tesseract.js runs OCR in 3 modes simultaneously and picks the best result
OCR text is cleaned (fixes common handwriting misreads like "60 w" to 60.00)
Groq AI reasons through the text and extracts the 4 fields
User reviews, edits if needed, and saves
Dashboard shows monthly spending by category
