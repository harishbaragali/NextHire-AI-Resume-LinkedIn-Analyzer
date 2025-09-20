NextHire · Frontend Prototype
================================

This minimal, framework‑free UI matches the provided spec: resume upload, LinkedIn URL input, job role selection, extracted text preview, and a results dashboard with placeholders. Buttons call stub API routes ready for backend wiring.

Files
-----
- `index.html` – layout and components
- `styles.css` – dark theme styling
- `app.js` – event handlers and API calls

Run locally
-----------
Open `index.html` directly, or serve the `web/` folder with a static server (needed for real API calls):

Python 3
```
python -m http.server 8080
```

Then open `http://localhost:8080/web/`.

API contract (placeholders)
---------------------------
- POST `/api/parse` – multipart/form-data with field `file`; returns `{ rawText, atsSuggestions }`
- POST `/api/analyze` – JSON `{ linkedinUrl?, role?, rawText? }`; returns `{ fitScore, atsSuggestions, highlights }`
- POST `/api/github-link` – JSON `{ url }`; returns `{ message }`

You can implement these in Node.js/Express, Flask/FastAPI, or any backend and deploy separately. Update `callApi()` base URL in `app.js` if your backend runs on a different origin.


# NextHire-AI-Resume-LinkedIn-Analyzer
