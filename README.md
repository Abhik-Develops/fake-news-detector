# Fake News Detector

This project includes a Chrome extension and a FastAPI backend for detecting fake news on webpages.

## Chrome Extension

### Features

- Auto-Screen: Automatically checks if the webpage is fake news when enabled.
- Manual Check: Allows users to manually check if the current webpage is fake news.

### Installation

1. Clone the repository:

    ```sh
    git clone https://github.com/abhik-develops/fake-news-detector.git
    cd fake-news-detector
    ```

2. Open Chrome and navigate to `chrome://extensions/`.

3. Enable "Developer mode" using the toggle switch in the top right corner.

4. Click on "Load unpacked" and select the `chrome-extension` directory from this repository.

5. The extension should now be installed and visible in your Chrome extensions list.

### Usage

1. Click on the Fake News Detector extension icon in the Chrome toolbar.

2. Toggle the "Auto-Screen" checkbox to enable or disable automatic screening.

3. Click the "Check This Page" button to manually check the current webpage for fake news.

## FastAPI Backend

### Features

- Analyzes the content of a webpage and determines if it contains fake news.
- Returns a detailed analysis of the text, image, and video content on the webpage.

### Installation

1. Clone the repository:

    ```sh
    git clone https://github.com/abhik-develops/fake-news-detector.git
    cd fake-news-detector/backend
    ```

2. Create a virtual environment and activate it:

    ```sh
    python3 -m venv venv
    source venv/bin/activate
    ```

3. Install the required dependencies:

    ```sh
    pip install fastapi
    ```

4. Run the FastAPI server:

    ```sh
    fastapi dev main.py
    ```

### Usage

1. The FastAPI server will be running at `http://127.0.0.1:8000`.
2. The server will return a JSON response with the analysis of the webpage.

### Example Response

```json
{
    "url": "http://www.example.com",
    "text": {
        "phrase_tool": "fake",
        "language_tool": "real",
        "commonsense_tool": "real",
        "standing_tool": "fake",
        "fact_check_tool": "TRUE"
    },
    "image": {
        "deepfake_tool": 0.5,
        "phrase_tool": "real",
        "language_tool": "real",
        "commonsense_tool": "fake",
        "standing_tool": "real"
    },
    "video": {
        "deepfake_tool": 0.5,
        "phrase_tool": "fake",
        "language_tool": "fake",
        "commonsense_tool": "real",
        "standing_tool": "fake"
    },
    "final_blockchain_score": 3,
    "final_ai_score": 2
}
