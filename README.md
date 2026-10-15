# Text Summarizer with Hugging Face BART

A Python and Flask web application that turns long text into shorter summaries using the Hugging Face inference API and `facebook/bart-large-cnn`.

## What it demonstrates

- Integrating a pretrained transformer model into a web application.
- Accepting source text and a maximum summary length through a browser form.
- Sending inference requests and displaying the generated summary.
- Packaging the application with Docker.

## How it works

The browser submits text to Flask's `/summarize` endpoint. Flask sends the text and length parameters to the model API, then renders the returned summary.

## Run locally

```bash
git clone https://github.com/yashwanthp21/TextSummarizer.git
cd TextSummarizer/TextSummarizer-using-huggingface-api/DataSummarizer-using-huggingface-api
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
export HF_TOKEN="your_hugging_face_token"
python app.py
```

On Windows PowerShell, activate with `.venv\Scripts\Activate.ps1` and set the token with `$env:HF_TOKEN="your_hugging_face_token"`.

Open http://127.0.0.1:5000, enter text, choose a summary length, and submit.

The application uses a legacy Hugging Face inference URL. A current token and an available model endpoint are required; the endpoint may need updating before inference works. The included Dockerfile uses Python 3.6, so dependency and runtime modernization may also be needed.

## Project files

| Path inside the application folder | Purpose |
| --- | --- |
| `app.py` | Flask routes and inference request |
| `webapp/templates/index.html` | Input form and summary display |
| `requirements.txt` | Python dependencies |
| `Dockerfile` | Container build definition |

## Credentials

Set `HF_TOKEN` in the runtime environment. Do not commit tokens. Any token previously committed to this repository must be revoked, because removing it from the current file does not remove it from Git history.

## Author

[Yashwanth Pulimi](https://github.com/yashwanthp21)
