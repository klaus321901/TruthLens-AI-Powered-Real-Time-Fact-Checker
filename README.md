# 📰 Fake News Detection

A fact-checking application built with FastAPI, Google Gemini API, and SerpAPI.
It accepts a claim, fetches live evidence from the web, and processes it for analysis.
Gemini then evaluates the context to return a verdict with reasoning, confidence score, and supporting evidence.
---

##  Features
- Accepts a claim as input (via API or frontend).  
- Fetches live web search results using **SerpAPI**.  
- Cleans and normalizes the claim text.  
- Passes evidence snippets into **Gemini 1.5 Flash** for structured reasoning.  
- Returns a structured verdict:

Final Verdict: REAL / FAKE / UNKNOWN
Score: Confidence (0–100)
Reasoning: Explanation of why
Evidence: Context snippets
Warnings: Weak/contradictory info if any

---

##  Project Structure
```text
.
├── main2.py                # FastAPI backend with fact-check pipeline  
├── requirements.txt       # Python dependencies  
├── landing_page/          # (Optional) UI assets / screenshots                                                                          ---
├── search_query_result/   # Stored snippets/screenshots from search  
└── README.md              # Documentation  
```
### 1. Clone the repository
```
git clone https://github.com/<your-username>/fake-news-detection.git
cd fake-news-detection
```
### 2. Create a virtual environment
```
python -m venv .venv
```
### 3. Activate the virtual environment
```
On Windows

.venv\Scripts\activate


On macOS/Linux

source .venv/bin/activate
```
### 4. Install dependencies
```
pip install -r requirements.txt
```

### 5. Create a .env file
```
GEMINI_API_KEY=your-gemini-api-key
SERPAPI_API_KEY=your-serpapi-api-key

```

### 6. Run the backend
```
uvicorn main2:app --reload

```
### API will be live at:
```
http://127.0.0.1:8000

```

 ### Example Usage
 ```
curl -X POST "http://127.0.0.1:8000/fact-check" \
-H "Content-Type: application/json" \
-d '{"claim": "The Eiffel Tower is in Paris"}'

```
 ### Sample Response
 ```
{
  "verdict": "REAL",
  "score": "95",
  "reasoning": "Multiple sources confirm the Eiffel Tower is in Paris.",
  "evidence": "- The Eiffel Tower is a landmark in Paris, France.",
  "warnings": ""
}

```
 
### API Endpoints
POST /fact-check   → Takes a claim and returns a fact-check result

### Tech Stack

-Python 3.10+

-FastAPI (backend framework)

-Google Gemini API (fact-check reasoning)

-SerpAPI (live web search results)

```
##  Frontend Setup (Angular)

### 1. Navigate to the frontend folder
cd fact-chex

```
###  2.Install dependencies
```
npm install

```
## 3. Run the Angular app
```
ng serve

```
### The frontend will be live at: 
http://localhost:4200

### Backend Setup (FastAPI)
Run the backend
```
uvicorn main2:app --reload
```
### The backend will be live at:
```
http://127.0.0.1:8000

```

### Connecting Frontend & Backend
The Angular frontend (http://localhost:4200) sends requests to the FastAPI backend (http://127.0.0.1:8000/fact-check).


## 📹 Demonstration Video
▶️[Watch Demo](https://drive.google.com/file/d/1CddCdDRE2-49zwdhRz3UDObEY5QJ60ae/view?usp=sharing)

---

## 📚 References

1. Shu, K., Sliva, A., Wang, S., Tang, J., & Liu, H. (2017). Fake News Detection on Social Media: A Data Mining Perspective. ACM SIGKDD Explorations Newsletter, 19(1), 22-     36.
   https://doi.org/10.1145/3137597.3137600

2. Zhou, X., & Zafarani, R. (2020). A Survey of Fake News: Fundamental Theories, Detection Methods, and Opportunities. ACM Computing Surveys, 53(5), 1–40.
   https://doi.org/10.1145/3395046

3. Google AI. Gemini LLM Documentation.
   https://ai.google.dev

## 🖼️ Assets / Screenshots

<img src="https://github.com/klaus321901/Fake_News_Detection/blob/259c8358997c63475913a524a28a2c6f80abc11c/Screenshot%20(715).png" width="700"/>

<img src="https://github.com/klaus321901/Fake_News_Detection/blob/ae7a3fded1fa1a9ec8714199077c0f6ce7b34454/Screenshot%20(405).png" width="700"/>

<img src="https://github.com/klaus321901/Fake_News_Detection/blob/ae7a3fded1fa1a9ec8714199077c0f6ce7b34454/Screenshot%20(406).png" width="700"/>










