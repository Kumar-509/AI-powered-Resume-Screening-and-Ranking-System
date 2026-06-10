# AI-powered Resume Screening and Ranking System

This project is an AI-powered Resume Screening and Ranking System designed to automate the hiring process by efficiently analyzing and ranking resumes based on predefined criteria. It leverages natural language processing and machine learning techniques to match resumes with job descriptions.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [How It Works](#how-it-works)
- [Key Components](#key-components)
- [Example Output](#example-output)
- [Requirements](#requirements)
- [Future Enhancements](#future-enhancements)

## 🎯 Overview

The AI Resume Screening and Ranking System automates the initial stages of recruitment by:
- **Parsing PDF Resumes**: Extracts text content from multiple PDF files
- **Analyzing Job Descriptions**: Understands requirements from job postings
- **Ranking Candidates**: Uses TF-IDF vectorization and cosine similarity to match resumes with jobs
- **Displaying Results**: Shows ranked results with similarity scores

This system reduces manual screening time and helps identify the best-matched candidates quickly.

## ✨ Features

- 📄 **PDF Resume Extraction**: Automatically extracts and processes text from PDF resumes
- 🔍 **Job Description Matching**: Analyzes resumes against job descriptions using NLP
- 📊 **Similarity Scoring**: Calculates relevance scores using cosine similarity
- 🎯 **Automatic Ranking**: Ranks candidates from most to least relevant
- 🖥️ **User-Friendly Interface**: Interactive web application built with Streamlit
- 📈 **Batch Processing**: Upload multiple resumes at once
- 💾 **Result Display**: Shows results in a sortable DataFrame

## 🛠️ Technology Stack

| Technology | Purpose |
|-----------|---------|
| **Python** | Core programming language |
| **Streamlit** | Web application framework for UI |
| **PyPDF2** | PDF file reading and text extraction |
| **scikit-learn** | TF-IDF vectorization and cosine similarity calculations |
| **Pandas** | Data manipulation and result display |

## 📁 Project Structure

```
AI-powered-Resume-Screening-and-Ranking-System/
├── README.md                 # Project documentation
└── Resume-Ranking.py         # Main application file
```

## 🚀 Installation

### Prerequisites
- Python 3.7 or higher
- pip (Python package manager)

### Setup Steps

1. **Clone the Repository**
   ```bash
   git clone https://github.com/Kumar-509/AI-powered-Resume-Screening-and-Ranking-System.git
   cd AI-powered-Resume-Screening-and-Ranking-System
   ```

2. **Create a Virtual Environment (Optional but Recommended)**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install Required Dependencies**
   ```bash
   pip install streamlit PyPDF2 pandas scikit-learn
   ```
   
   Or install from requirements (if available):
   ```bash
   pip install -r requirements.txt
   ```

## 💻 Usage

1. **Run the Application**
   ```bash
   streamlit run Resume-Ranking.py
   ```

2. **Access the Web Interface**
   - Open your browser and navigate to `http://localhost:8501`

3. **How to Use**
   - **Enter Job Description**: Paste or type the job description in the text area
   - **Upload Resumes**: Select multiple PDF files containing candidate resumes
   - **View Results**: The system automatically ranks and displays results with similarity scores
   - **Sort Results**: Results are automatically sorted by score in descending order

## 🔧 How It Works

### Algorithm Overview

1. **Text Extraction**
   - Reads PDF files using PyPDF2
   - Extracts all text from PDF pages
   - Handles multiple resumes in batch

2. **TF-IDF Vectorization**
   - Converts job description and resumes into numerical vectors
   - Uses TF-IDF (Term Frequency-Inverse Document Frequency) weighting
   - Captures the importance of terms in documents

3. **Cosine Similarity Calculation**
   - Computes cosine similarity between job description vector and each resume vector
   - Similarity scores range from 0 to 1
   - Higher scores indicate better matches

4. **Ranking and Display**
   - Sorts candidates by similarity score in descending order
   - Displays results in a pandas DataFrame
   - Shows resume filenames and corresponding scores

### Code Workflow

```
User Input (Job Description + Resumes)
         ↓
PDF Text Extraction (extract_text_from_pdf)
         ↓
TF-IDF Vectorization (rank_resumes)
         ↓
Cosine Similarity Calculation
         ↓
Score Ranking (sort by descending score)
         ↓
Results Display (Streamlit DataFrame)
```

## 🔑 Key Components

### `extract_text_from_pdf(file)`
**Purpose**: Extracts text content from PDF files

**Parameters**:
- `file`: PDF file object

**Returns**:
- `text`: Extracted text string

**Process**:
- Creates PdfReader object from file
- Iterates through all pages
- Extracts text from each page
- Concatenates all text

### `rank_resumes(job_description, resumes)`
**Purpose**: Ranks resumes based on similarity to job description

**Parameters**:
- `job_description`: String containing job requirements
- `resumes`: List of resume text strings

**Returns**:
- `cosine_similarities`: Array of similarity scores

**Process**:
- Combines job description with all resumes
- Applies TF-IDF vectorization
- Calculates cosine similarity between job description and each resume
- Returns normalized similarity scores

### Streamlit Interface
**Elements**:
- Title and headers for organization
- Text area for job description input
- File uploader for multiple PDFs
- Results table with ranking

## 📊 Example Output

When you run the application with sample data, you'll see output similar to:

| Resume | Score |
|--------|-------|
| candidate_a.pdf | 0.8743 |
| candidate_b.pdf | 0.7521 |
| candidate_c.pdf | 0.6892 |
| candidate_d.pdf | 0.5234 |

*Note: Scores represent the similarity between the resume and job description (0-1 scale)*

## 📦 Requirements

Create a `requirements.txt` file with:

```
streamlit==1.28.0
PyPDF2==3.0.1
pandas==2.1.1
scikit-learn==1.3.2
```

Install all dependencies at once:
```bash
pip install -r requirements.txt
```

## 🚀 Future Enhancements

- 🤖 **Advanced NLP**: Integrate transformer-based models (BERT, GPT) for better understanding
- 🎯 **Weighted Criteria**: Allow custom weighting for specific skills and experience
- 💾 **Database Integration**: Store and manage job postings and candidate profiles
- 📧 **Email Notifications**: Notify selected candidates automatically
- 🔐 **Security Features**: Add user authentication and role-based access
- 📱 **API Development**: Create REST API for integration with HR systems
- 🌐 **Multi-language Support**: Support resumes in different languages
- 📈 **Analytics Dashboard**: Provide hiring analytics and insights
- 🎨 **Enhanced UI**: Improve UI/UX with advanced visualizations
- ⚙️ **Custom Models**: Train custom ML models for specific industries

## 📝 Notes

- PDF extraction quality depends on the resume format and PDF structure
- Scores are based on keyword and phrase matching, not semantic understanding
- Ensure job descriptions are detailed for better matching results
- Text formatting in PDFs may affect extraction accuracy

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs and issues
- Suggest new features
- Improve documentation
- Submit pull requests

## 📄 License

This project is open-source and available for educational and commercial use.

## 👨‍💻 Author

**Kumar-509**

---

**Made with ❤️ for the hiring community**

---

*Last Updated: 2026*
