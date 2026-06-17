# Agentic Chronic Patient Monitoring — SRA System

Minimal repository for running the chronic patient monitoring project.

## Requirements

* Python 3.10 to 3.12
* `pip`
* Optional: Gemini API key for generated clinical notes and email narratives

## Files You Need

```text
02_src/
03_dashboard/streamlit_app.py
config.yaml
data/eicu_real_cohort.csv
main.py
requirements.txt
smtp_settings.local.example.json
```

## Install

```bash
git clone https://github.com/Valkyiri/Agentic-Chronic-Patient-Monitoring-SRA-System.git
cd Agentic-Chronic-Patient-Monitoring-SRA-System
pip install -r requirements.txt
```

## Optional Gemini API Key

Linux/macOS:

```bash
export GEMINI_API_KEY="your_key_from_aistudio.google.com"
```

Windows PowerShell:

```powershell
$env:GEMINI_API_KEY="your_key_from_aistudio.google.com"
```

## Run

### Full pipeline

```bash
python main.py --patient-limit 200
```

### Streamlit dashboard

```bash
streamlit run 03_dashboard/streamlit_app.py
```

### FastAPI server

```bash
uvicorn main:app --reload --port 8000
```

API docs:

```text
http://localhost:8000/docs
```

## Useful Options

```bash
python main.py --patient-limit 200 --skip-shap
python main.py --patient-limit 80 --keep-logs
```

## Output

Runtime outputs such as predictions, monitoring feeds, and audit artifacts are written to `logs/` during execution.
