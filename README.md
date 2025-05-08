# 📚 Notes Sage - Gemini-Powered Lecture Notes Chatbot

This project is an intelligent chatbot built with **LangChain**, **Google Gemini API**, and **Chroma vector database**, designed to help you query your **lecture notes** in natural language. The app uses **PDF parsing**, **chunking**, **vector embeddings**, and **retrieval-based QA**, all within a user-friendly **Google Colab notebook interface**.

---

## 🚀 Features

- 🔐 Secure API key input for Gemini models
- 📄 Load and process PDF lecture notes from Google Drive
- ✂️ Smart chunking using `RecursiveCharacterTextSplitter`
- 📦 Store document chunks using **Chroma Vector Store**
- 🧠 Embedding powered by `GoogleGenerativeAIEmbeddings`
- 💬 Conversational Q&A using Gemini (`gemini-2.0-flash`)
- 🧾 Interactive chatbot UI with `ipywidgets` in Colab
- 🔁 Source-aware responses using `RetrievalQA`

---

## 📁 Project Structure

```plaintext
📁 /content/drive/MyDrive/CTSE/CTSE_Lecture_Notes.pdf   # input lecture notes PDF
📄 main_colab_notebook.ipynb                            # Core notebook with chatbot implementation
📦 ./chroma_db                                          # Persistent vector DB with embedded chunks
```

---

## 🛠️ Setup Instructions

1. **Open the notebook in Google Colab**

2. **Install required packages**

   ```python
   %pip install --upgrade langchain-chroma
   %pip install -q ipywidgets
   ```

3. **Run the notebook cells in order**

4. **When prompted**, securely enter your Gemini API key:

   ```python
   Enter API key for Google Gemini:
   ```

5. **Ensure your CTSE lecture PDF is located at:**
   ```
   /content/drive/MyDrive/CTSE/CTSE_Lecture_Notes.pdf
   ```

---

## 🧠 How It Works

1. **PDF Loading**  
   Loads and extracts text from your CTSE PDF using `PyPDFLoader`.

2. **Chunking**  
   Breaks text into overlapping chunks (`chunk_size=1000`, `overlap=200`) for better context understanding.

3. **Embedding**  
   Uses Gemini's `embedding-001` model to convert text chunks into vector space.

4. **Vector Storage**  
   Stores vectors in ChromaDB (`./chroma_db`) for persistent retrieval.

5. **Retrieval + LLM**  
   Uses `RetrievalQA` with `gemini-2.0-flash` to generate natural language answers from the vector index.

6. **Interactive Chat UI**  
   Accepts user input and renders Q&A messages in a styled widget output area.

---

## 📸 Demo Screenshot

> _(Add a screenshot or GIF of your chatbot interface in action here for better visual appeal)_

---

## 📚 Example Questions You Can Ask

- “What are the main topics covered in Software Project Management?”
- “Explain the waterfall model.”
- “How does Agile differ from traditional models?”

---

## 📌 Dependencies

- `langchain`
- `langchain_chroma`
- `langchain_google_genai`
- `ipywidgets`
- `google.colab`
- `PyPDFLoader` (from `langchain_community.document_loaders`)

---

## 🧑‍💻 Author

**👨‍🎓 [Your Name]**  
Built for CTSE students to improve lecture note interaction using the latest in LLM technology.

---

## 📄 License

MIT License – feel free to use, modify, and share.
