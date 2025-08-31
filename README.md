 AI Resume Screening API

An AI-powered resume screening and candidate-job matching system built with FastAPI, SpaCy, and SentenceTransformers.
This project extracts structured information (name, skills, experience, education) from resumes (PDF/DOCX/TXT), evaluates them against job descriptions, and provides match scores, rankings, and detailed insights into candidate-job fit.

 Features
	•	Resume Parsing → Extracts name, email, phone, skills, experience, and education.
	•	AI Job Matching → Uses semantic similarity (BERT), skill matching, and experience analysis.
	• Candidate Ranking → Ranks multiple candidates against job descriptions.
	•	REST API with FastAPI → Upload resumes, parse, match, and rank candidates.
	•	CORS Enabled → Easy integration with frontend apps.
	•	In-Memory DB → Stores uploaded candidates (swap with PostgreSQL/MongoDB if needed).



 Tech Stack
	•	Backend → FastAPI, Uvicorn
	•	NLP/AI → SpaCy, SentenceTransformers (all-MiniLM-L6-v2)
	•	File Processing → PyPDF2, python-docx
	•	ML → scikit-learn (cosine similarity)
	•	Other → Regex-based parsing, JSON APIs



 Installation

# 1. Clone the repo
git clone https://github.com/your-username/ai-resume-screening-api.git
cd ai-resume-screening-api

# 2. Create virtual environment
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows

# 3. Install dependencies
pip install -r requirements.txt

# 4. Download SpaCy model
python -m spacy download en_core_web_sm

# 5. Run the server
uvicorn main:app --reload


 API Endpoints

1️⃣ Root

GET / → API metadata & available endpoints.

2️⃣ Parse Resume

POST /parse-resume → Upload a resume → returns structured candidate info.

3️⃣ Upload Resume

POST /upload-resume → Store candidate in DB → returns ID + parsed info.

4️⃣ Match Job

POST /match-job → job_title + job_description → returns score breakdown.

5️⃣ Rank Candidates

POST /rank-candidates → Ranks all uploaded candidates for a job.

6️⃣ Get Candidates

GET /candidates → List all uploaded candidates.

7️⃣ Delete Candidate

DELETE /candidates/{id} → Remove a candidate.

8️⃣ Clear DB

DELETE /candidates → Remove all candidates.

9️⃣ Health Check

GET /health → System health & loaded models.


 Example Usage

Upload Resume:

curl -X POST "http://127.0.0.1:8000/upload-resume" -F "file=@resume.pdf"

Match Job:

curl -X POST "http://127.0.0.1:8000/match-job" \
-F "job_title=AI Engineer" \
-F "job_description=Looking for Python, NLP, and ML experience"



Project Structure

├── main.py              # FastAPI app with endpoints
├── requirements.txt     # Dependencies
├── README.md            # Documentation
└── (models, uploads..)  # Future extensions


 Future Improvements
	•	PostgreSQL / MongoDB integration
	•	OCR for image-based resumes
	•	Advanced NER models for better skill extraction
	•	Recruiter dashboard frontend

##  Authors  
**Disha Davey**  
[dishdavey2111@gmail.com](mailto:dishdavey2111@gmail.com)  
[GitHub](https://github.com/Dishdavey21) 
**Kanishka Patwal**
[GitHub](https://github.com/Kanishka29-k)
**Khushi Chelani**
[GitHub](https://github.com/Khushichelani-28)
