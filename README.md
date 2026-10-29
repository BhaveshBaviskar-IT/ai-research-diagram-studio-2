#  AI Research Diagram Studio

### AI-Powered Academic Diagram Generation using IBM Granite, React, Flask, and LaTeX TikZ

AI Research Diagram Studio is a web-based application that transforms natural language prompts into structured academic and technical diagrams using IBM Granite AI. It generates LaTeX TikZ code to help students, researchers, and developers create diagrams for research papers, technical documentation, and academic projects.

## ✨ Features

- **AI-Powered Generation:** Uses IBM Granite AI through IBM watsonx.ai to generate diagram code from text prompts.
- **Natural Language Input:** Describe a diagram in simple English.
- **Multiple Diagram Types:** Supports prompts for flowcharts, UML diagrams, neural networks, binary trees, ER diagrams, and system architectures.
- **TikZ Code Generation:** Produces LaTeX TikZ code for generated diagrams.
- **Interactive Web Interface:** Built with React, Vite, and Material UI.
- **PDF Compilation:** Supports PDF generation when a compatible LaTeX compiler is available.
- **Online Deployment:** Frontend hosted on Vercel and backend hosted on Render.

## 🛠️ Technology Stack

| Component | Technology |
|---|---|
| Frontend | React.js, Vite |
| UI Framework | Material UI |
| Backend | Python, Flask |
| AI Model | IBM Granite through IBM watsonx.ai |
| Diagram Generation | LaTeX TikZ |
| PDF Compilation | pdfLaTeX |
| API Communication | Axios |
| Frontend Hosting | Vercel |
| Backend Hosting | Render |

## 🏗️ System Architecture

```text
          User
           |
           v
   React + Vite Frontend
           |
           v
       Flask API
           |
           v
     IBM Granite AI
           |
           v
      TikZ Code
           |
           v
   LaTeX PDF Compiler
           |
           v
     PDF Diagram
```

**Note:** PDF generation requires `pdflatex` to be installed and accessible. On cloud deployments without a LaTeX compiler, TikZ code can still be generated, but PDF output may be unavailable.

## 📂 Project Structure

```text
ai-research-diagram-studio/
│
├── backend/
│   ├── app.py
│   ├── services/
│   │   └── granite_service.py
│   ├── compiler/
│   │   └── latex_compiler.py
│   ├── generated/
│   └── requirements.txt
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── services/
│   │   ├── styles/
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── index.html
│   ├── package.json
│   └── vite.config.js
│
├── .gitignore
├── package.json
└── README.md
```

*The structure above represents the main application components; some folders may differ in your repository.*

## ⚙️ Prerequisites

Install the following before running the project locally:

- Python 3.10 or a compatible version supported by the dependencies
- Node.js and npm
- An IBM Cloud account with access to IBM watsonx.ai
- IBM API credentials and a valid project ID
- A LaTeX distribution with `pdflatex`, if PDF generation is required

## 🚀 Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/BhaveshBaviskar-IT/ai-research-diagram-studio.git
cd ai-research-diagram-studio
```

### 2. Configure the Backend

```bash
cd backend
pip install -r requirements.txt
```

Create a `.env` file inside the `backend` directory:

```env
IBM_URL=your_ibm_watsonx_url
IBM_API_KEY=your_ibm_api_key
IBM_PROJECT_ID=your_ibm_project_id
```

Replace the placeholder values with your own valid credentials. Never upload your `.env` file or API keys to GitHub.

Start the Flask backend:

```bash
python app.py
```

The backend will run locally at:

`http://127.0.0.1:5000`

### 3. Configure the Frontend

Open a second terminal:

```bash
cd frontend
npm install
npm run dev
```

Open the local Vite URL displayed in your terminal, typically:

`http://localhost:5173`

Ensure the frontend API configuration points to the correct backend URL.

## 🔌 API Endpoint

### Generate Diagram

**Endpoint:** `POST /generate`

**Request body:**

```json
{
  "prompt": "Create a flowchart showing the machine learning lifecycle."
}
```

**Example response:**

```json
{
  "tikz": "\\begin{tikzpicture} ... \\end{tikzpicture}",
  "pdf": null,
  "tex": null
}
```

The `pdf` and `tex` fields depend on the backend implementation. If PDF compilation is enabled, the response may contain generated file references instead of `null`.

## 💡 Example Prompts

Try these prompts in the application:

1. **Machine Learning Lifecycle:** Create a flowchart showing data collection, preprocessing, feature engineering, model training, evaluation, deployment, and monitoring.
2. **Cloud Computing Architecture:** Generate an architecture diagram showing clients, cloud services, application servers, databases, and storage.
3. **Library Management System:** Create a UML class diagram with Book, Member, Librarian, and Loan classes, including their relationships.
4. **Neural Network:** Generate a neural network architecture with an input layer, two hidden layers, and an output layer.
5. **Database Design:** Create an ER diagram for a student management system with Student, Course, Faculty, and Enrollment entities.

## 🌐 Deployment

- **Frontend:** Deploy the `frontend` directory using Vercel with the Vite framework.
- **Backend:** Deploy the Flask application using Render, with the backend directory configured as the service root where appropriate.
- **Environment Variables:** Configure `IBM_URL`, `IBM_API_KEY`, and `IBM_PROJECT_ID` in the backend hosting provider.
- **CORS:** Configure backend CORS to allow requests from the deployed frontend domain.
- **PDF Support:** Install a compatible LaTeX distribution or use a separate PDF compilation service if cloud PDF generation is required.

## 🔐 Security

- Store API credentials in environment variables.
- Never commit `.env` files, API keys, or private credentials.
- Validate user prompts and handle API errors appropriately.
- Restrict cross-origin requests to trusted frontend domains in production.
- Avoid exposing internal server errors or sensitive configuration details to users.

## 🎯 Project Objectives

- Simplify academic and technical diagram creation.
- Reduce the time needed to prepare diagrams for research papers and reports.
- Demonstrate the practical use of IBM Granite generative AI.
- Combine natural language processing with LaTeX-based diagram generation.
- Provide a web-based tool for students, researchers, and developers.

## 🔮 Future Enhancements

- Browser-based diagram previews.
- Improved PDF and PNG export.
- Editable diagram layouts.
- User authentication and cloud-based project storage.
- More diagram templates and customizable themes.
- Better prompt validation and automatic correction of invalid TikZ code.

## 👨‍💻 Author

**Bhavesh Baviskar**

GitHub: [@BhaveshBaviskar-IT](https://github.com/BhaveshBaviskar-IT)

Project Repository: [AI Research Diagram Studio](https://github.com/BhaveshBaviskar-IT/ai-research-diagram-studio)

## 📄 License

Choose and add an appropriate open-source license before distributing this project publicly.

---

*Developed as an AI-powered academic diagram generation project using IBM Granite and modern web technologies.*
