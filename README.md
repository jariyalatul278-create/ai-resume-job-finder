# AI Resume Builder & Live Job Recommendation

A Python CLI app that collects a candidate's details through an AI chat, generates a professional PDF resume, and finds real, open jobs on the internet using AI web search.

## Features

- **Conversational data collection:** an OpenAI chat model asks 15 questions one at a time (name, contact, education, experience, skills, projects, certifications, job preferences, expected salary) and returns structured JSON.
- **PDF resume generation:** builds a clean, formatted resume with ReportLab.
- **Live job recommendations:** uses OpenAI's web search tool to find current openings (Naukri, LinkedIn, Indeed, Internshala, etc.) with a match percentage, matching and missing skills, and an apply link.
- **SMS alert (optional):** sends the top job link to the candidate's phone through an SMS gateway.

## Tech Stack

Python, OpenAI API (Chat Completions and Responses with web search), ReportLab, python-dotenv, Requests

## Setup

1. Clone the repo
   ```bash
   git clone https://github.com/<your-username>/<repo-name>.git
   cd <repo-name>
   ```

2. Create a virtual environment and install dependencies
   ```bash
   python -m venv venv
   source venv/bin/activate      # Windows: venv\Scripts\activate
   pip install -r requirements.txt
   ```

3. Create a `.env` file (see `.env.example`) and add your keys
   ```
   OPENAI_API_KEY=...
   SMSWORLD_URL=...        # optional
   SMSWORLD_AUTHKEY=...    # optional
   SMSWORLD_SENDER=...     # optional
   ```

4. Run
   ```bash
   python main.py
   ```

## How it works

1. The assistant asks for your details one question at a time.
2. A resume is saved as `Generated_Resume.pdf`.
3. The AI searches the web for matching jobs and prints the top 5 sorted by match percentage.
4. If SMS credentials are set, the top job link is sent to your phone.

## Notes

- Never commit your `.env` file. It is already listed in `.gitignore`.
- The SMS message uses a pre-approved template. Update `TEMPLATE` in `main.py` to match your own approved template.
- Job results come from AI web search, so always verify the apply link before applying.
