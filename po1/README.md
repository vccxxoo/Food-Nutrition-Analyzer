# Nutrition App (Frontend + Backend)

This folder contains a simple frontend (HTML/CSS/JS) and a backend (Flask) that analyzes a food photo.
The backend will use Hugging Face inference + USDA FoodData Central if you provide API keys, otherwise it returns demo values.

## Files
- index.html — frontend UI (open with Live Server)
- style.css — styles
- script.js — frontend logic (sends image to backend)
- server.py — Flask backend: /analyze endpoint
- requirements.txt — Python dependencies

## Run locally (VS Code)
1. Install Python 3.9+ and create a virtual env (optional but recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate   # mac/linux
   venv\Scripts\activate    # windows (cmd)
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. (Optional) Set API keys as environment variables to enable real predictions:
   ```bash
   export HF_API_KEY='your_hf_key'    # mac/linux
   set HF_API_KEY=your_hf_key         # windows cmd
   # and for USDA key:
   export USDA_API_KEY='your_usda_key'
   ```
   Or create a file `config.py` with:
   ```python
   HF_API_KEY = 'your_hf_key'
   USDA_API_KEY = 'your_usda_key'
   ```
4. Start the backend:
   ```bash
   python server.py
   ```
5. Open `index.html` using Live Server in VS Code (right-click → Open With Live Server).
6. Upload an image and press Analyze. The frontend will call the backend at `http://127.0.0.1:5000/analyze`.

## Notes
- Keep your API keys private. Do not commit them to public repositories.
- If Hugging Face model is cold, the first inference may be slow.
