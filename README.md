# AI-Attention-Visualization

AI Attention Visualization is a Python-based application that demonstrates how an AI model can identify and visualize the attention given to words in an image containing study notes.

The application uses OCR to extract text from an uploaded image, processes the extracted words, generates embeddings, calculates attention scores, and displays the attention given to each word.

## Project Workflow

```text
Study Notes Image
        ↓
      OCR
        ↓
 Text Extraction
        ↓
  Word Processing
        ↓
    Embeddings
        ↓
 Attention Calculation
        ↓
 Word Attention Scores
```

## Features

* Upload study-notes images in JPG, JPEG, or PNG format
* Extract text from images using OCR
* Clean and process extracted words
* Generate word embeddings
* Calculate attention scores using Query, Key, and Value representations
* Display attention scores using progress bars
* Identify the word with the highest attention score
* Interactive web interface using Streamlit

## Technologies Used

* Python
* Streamlit
* NumPy
* Pillow
* Tesseract OCR
* PyTesseract
* Sentence Transformers

## Project Structure

```text
AI-Attention-Visualization/
│
├── app.py
├── ocr.py
├── attention.py
├── requirements.txt
├── Output.pdf
└── README.md
```

## How It Works

### 1. Image Upload

The user uploads a study-notes image through the Streamlit interface.

### 2. OCR

Tesseract OCR extracts the text from the uploaded image.

### 3. Word Processing

The extracted text is split into individual words. Punctuation is removed and short words are filtered out. The application processes a maximum of 20 words.

### 4. Embeddings

The processed words are converted into numerical vector representations using a sentence-transformer model.

### 5. Attention Calculation

The embeddings are used to generate Query, Key, and Value representations.

The attention score is calculated using:

```text
Attention(Q, K, V) = Softmax(QKᵀ / √dₖ)V
```

The implementation calculates attention weights and averages them to obtain a score for each word.

### 6. Visualization

The attention scores are normalized and displayed as progress bars for each processed word.

The application also displays the word with the highest attention score.

## Installation

Clone the repository:

```bash
git clone https://github.com/aarthy2411/AI-Attention-Visualization.git
```

Move into the project directory:

```bash
cd AI-Attention-Visualization
```

Install the required Python packages:

```bash
pip install -r requirements.txt
```

## Tesseract OCR Setup

Tesseract OCR is required for extracting text from images.

On Windows, install Tesseract OCR and make sure the executable path is correctly configured in `ocr.py`.

Example:

```python
pytesseract.pytesseract.tesseract_cmd = (
    r"C:\Program Files\Tesseract-OCR\tesseract.exe"
)
```

## Run the Application

Start the Streamlit application using:

```bash
python -m streamlit run app.py
```

The application will open in the browser.

## Output

The application displays:

* Uploaded image
* Extracted text
* Processed words
* Embedding creation status
* Word attention scores
* Highest attention word

## Attention Calculation

The attention mechanism implemented in this project follows the basic scaled dot-product attention concept.

The process involves:

```text
Embeddings
    ↓
Query (Q)
Key (K)
Value (V)
    ↓
Q × Kᵀ
    ↓
Scaling
    ↓
Softmax
    ↓
Attention Weights
    ↓
Word Attention Scores
```

## Purpose of the Project

This project provides a simple visual demonstration of how attention mechanisms can be applied to text extracted from images. It helps in understanding the connection between embeddings, attention calculations, and word-level importance.

## Author

**Aarthy**
