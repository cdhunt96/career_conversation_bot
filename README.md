# Career Conversation Bot

A Gradio-based chatbot that represents Christian Hunt for career-related conversations. The bot uses OpenAI's GPT-4o-mini model with function calling to answer questions about career, background, skills, and experience.

## Features

- Interactive chat interface powered by Gradio
- Uses OpenAI GPT-4o-mini with function calling
- Records user details and unknown questions via Pushover notifications
- Loads resume and summary information from local files

## Setup

1. **Install dependencies** (using uv):
   ```bash
   uv sync
   ```

   Or using pip:
   ```bash
   pip install -r requirements.txt
   ```

2. **Configure environment variables**:
   ```bash
   cp .env.example .env
   ```
   Then edit `.env` and add your:
   - `OPENAI_API_KEY` - Your OpenAI API key
   - `PUSHOVER_TOKEN` - Your Pushover app token (optional, for notifications)
   - `PUSHOVER_USER` - Your Pushover user key (optional, for notifications)

3. **Ensure resume file exists**:
   Make sure `me/christianresume.pdf` exists in the project directory.

## Running

```bash
uv run app.py
```

Or with Python directly:
```bash
python app.py
```

The app will start a Gradio interface, typically at `http://127.0.0.1:7860`.

## Project Structure

```
career_conversation_bot/
├── app.py              # Main application file
├── me/
│   ├── summary.txt     # Personal summary text
│   └── christianresume.pdf  # Resume PDF
├── pyproject.toml      # Project dependencies (uv)
├── .env.example        # Example environment variables
├── .gitignore          # Git ignore rules
└── README.md           # This file
```

## Deployment

For deployment to platforms like Hugging Face Spaces:
1. Set environment variables as secrets in your deployment platform
2. Ensure all files in `me/` directory are included in the deployment
3. The app will automatically use the environment variables from the platform
