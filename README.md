

# AI Resume Screening API

An AI-powered API for automated resume screening using FastAPI and SpaCy.  
This project helps extract and analyze key resume details for efficient hiring decisions.

---

## Features
- Resume parsing and keyword extraction  
- Skill and experience matching  
- FastAPI-based lightweight API  
- Easy setup and deployment  

---

## Installation

### 1. Clone the repository

git clone https://github.com/your-username/ai-resume-screening-api.git
cd ai-resume-screening-api

2. Create a virtual environment

python -m venv venv
 Activate it
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows

3. Install dependencies

pip install -r requirements.txt

4. Download SpaCy model

python -m spacy download en_core_web_sm

5. Run the server

uvicorn main:app --reload


⸻

## API Endpoints:
	•	POST /upload-resume/ → Upload a resume for parsing and analysis
	•	GET /health → Check API health status

## Example Request

curl -X POST "http://127.0.0.1:8000/upload-resume/" \
  -H "Content-Type: multipart/form-data" \
  -F "file=@resume.pdf"

Example Response

{
  "name": "John Doe",
  "email": "johndoe@email.com",
  "skills": ["Python", "Machine Learning", "SQL"],
  "experience": "3 years"
}


##  Authors  
**Disha Davey**  
[dishdavey2111@gmail.com](mailto:dishdavey2111@gmail.com) [GitHub](https://github.com/Dishdavey21) 
**Kanishka Patwal**
[GitHub](https://github.com/Kanishka29-k)
**Khushi Chelani**
[GitHub](https://github.com/Khushichelani-28)
