# Google Gemini Agent POC

This project demonstrates how to use Google Gemini's generative AI and agent tools to analyze soccer team performance using Python. It leverages the `google-genai` and `google-adk` libraries to create agents that search for recent soccer match results and calculate performance metrics.

## Features

- **Agent 1:** Searches for the last 10 official games of a given soccer team using Google Search.
- **Agent 2:** Analyzes the results and calculates the team's percentage of success.
- Interactive Jupyter Notebook interface.
- Uses environment variables for secure API key management.

## Requirements

- Python 3.10+
- Jupyter Notebook or JupyterLab
- Google API Key with access to Gemini

## Installation

1. **Clone the repository:**

   ```sh
   git clone https://github.com/yourusername/GoogleGeminiPOC.git
   cd GoogleGeminiPOC
   ```

2. **Install dependencies:**

   In a notebook cell or terminal:
   ```python
   %pip install google-genai google-adk python-dotenv
   ```

3. **Set up your API key:**

   Create a `.env` file in the project root with:
   ```
   GOOGLE_API_KEY=your_google_api_key_here
   ```

## Usage

1. **Open `GoogleGeminiAgent.ipynb` in Jupyter.**

2. **Run all cells.**  
   The notebook will:
   - Load your API key from `.env`
   - Ask you for the name of a soccer team
   - Use Agent 1 to fetch the last 10 games
   - Use Agent 2 to calculate the percentage of success
   - Display the results in a formatted table and summary

## How it Works

- **Session Management:**  
  Uses `InMemorySessionService` to manage agent sessions.
- **Agents:**  
  - `agent_search`: Uses Google Search to get recent match results.
  - `agent_perc_success`: Calculates the team's success percentage based on match outcomes.
- **Display:**  
  Results are shown using Markdown formatting for readability.

## Example

```
🚀 Starting the agent to get information of the last 10 games of soccer team 🚀
❓ Please enter the name of the soccer team: Flamengo

--- Result of Agent 1 (Searcher of Games) ---
> | Date       | Opponent | Result | W/L |
> |------------|----------|--------|-----|
> | 01/06/2025 | Team A   | 2-1    | W   |
> ...

--- 📝 Result of Agent 2 (Metrics for the results) ---
> The percentage of success is 73%.
```

## Troubleshooting

- **Session not found error:**  
  Make sure you do not create a new `InMemorySessionService` for each call. Use a single instance throughout the notebook.

- **API Key errors:**  
  Ensure your `.env` file is present and contains a valid `GOOGLE_API_KEY`.

## License

MIT License

---

**Note:** This project is for demonstration purposes and may require additional configuration for production use.