# Chatbot
---
ChartBot is a web-based AI chatbot application designed to assist users with concise and relevant answers to their queries. Built with Flask and leveraging Generative AI, the bot processes input questions and provides thoughtful responses under 150 words. If an answer cannot be generated, it suggests rephrasing the query or contacting support.

## Features
- Supports multiple input sources for system instructions: PDF, Word (`.docx`), text files, and web URLs.
- Processes user queries using a Generative AI model (`gemini-1.5-pro`).
- Delivers clear, concise, and sanitized chatbot responses.
- REST API endpoint for integrating with external applications.
- CORS-enabled for seamless cross-origin access.
- Logs user requests and AI responses for debugging and analytics.

## Tech Stack
- **Backend**: Flask
- **AI Integration**: Google Generative AI API
- **Libraries**:
  - `PyPDF2`: PDF text extraction
  - `docx`: Word file processing
  - `requests`, `BeautifulSoup`: Web scraping
  - `Flask-CORS`: Cross-Origin Resource Sharing
  - `re`: Regular expressions for text processing

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/smartbot.git
   cd smartbot
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Set the environment variable for your Google Generative AI API key:
   ```bash
   export GEMINI_API_KEY="your_api_key_here"
   ```

4. Ensure any required system instruction file (`data.docx`, `data.pdf`, `data.txt`) or URL is available in the appropriate location.

## Running the Application

1. Start the Flask application:
   ```bash
   python app.py
   ```

2. Open your browser and navigate to:
   ```
   http://localhost:5000
   ```

## API Usage

### Endpoint: `/api/chatbot/GetResponse`

- **Method**: `POST`
- **Headers**: 
  - `Content-Type: application/json`
- **Body**:
  ```json
  {
    "text": "Your query here"
  }
  ```
- **Response**:
  ```json
  {
    "response": "Chatbot's response"
  }
  ```

## Configuration

- Modify `generation_config` in `app.py` to fine-tune the chatbot's response style:
  - `temperature`: Controls randomness.
  - `top_p` and `top_k`: Control response diversity.
  - `max_output_tokens`: Sets the response length limit.

## Development Notes

- Logs are enabled at the `DEBUG` level for easier debugging.
- Add your templates (e.g., `index1.html`) under the `templates` directory.

## Limitations
- Currently supports only `.pdf`, `.docx`, and `.txt` file formats for system instructions.
- System instruction URL must be accessible and contain readable content.
- Responses are limited to 150 words.

## Contributing

Pull requests are welcome. For major changes, please open an issue to discuss the proposed changes.

## License

This project is licensed under the MIT License.

---
