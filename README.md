# 🌾 GREENY - Smart Agriculture AI Chatbot# 



[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

[![Python 3.10+](https://img.shields.io/badge/Python-3.10%2B-blue)](https://www.python.org/)[![Python 3.10+](https://img.shields.io/badge/Python-3.10%2B-blue)](https://www.python.org/)

[![Node.js 18+](https://img.shields.io/badge/Node.js-18%2B-green)](https://nodejs.org/)[![Node.js 18+](https://img.shields.io/badge/Node.js-18%2B-green)](https://nodejs.org/)

[![FastAPI](https://img.shields.io/badge/FastAPI-0.104%2B-009688?logo=fastapi)](https://fastapi.tiangolo.com/)[![FastAPI](https://img.shields.io/badge/FastAPI-0.104%2B-009688?logo=fastapi)](https://fastapi.tiangolo.com/)

[![React](https://img.shields.io/badge/React-18%2B-61DAFB?logo=react)](https://react.dev/)[![React](https://img.shields.io/badge/React-18%2B-61DAFB?logo=react)](https://react.dev/)



> An AI-powered greenhouse farming assistant for Tunisian farmers, supporting Tunisian Derja dialect and French with RAG (Retrieval-Augmented Generation) capabilities powered by OpenAI GPT.

## 🎯 Overview## 🎯 Overview



GREENY is a web-based intelligent chatbot designed specifically for **greenhouse farmers in Tunisia**. It provides expert agricultural advice in their native language (Tunisian Derja) and French, with personalized responses based on their greenhouse profile and uploaded documents.GREENY is a web-based intelligent chatbot designed specifically for **greenhouse farmers in Tunisia**. It provides expert agricultural advice in their native language (Tunisian Derja) and French, with personalized responses based on their greenhouse profile and uploaded documents.



### Key Highlights### Key Highlights

- 🗣️ **Native Language Support**: Tunisian Derja (دارجة تونسية) + French + English- 🗣️ **Native Language Support**: Tunisian Derja (دارجة تونسية) + French + English

- 📚 **RAG-Powered**: Retrieves answers from user documents + global knowledge base- 📚 **RAG-Powered**: Retrieves answers from user documents + global knowledge base

- 👥 **Personalized**: Adapts advice to greenhouse type, crops, region, and experience- 👥 **Personalized**: Adapts advice to greenhouse type, crops, region, and experience

- 📎 **Cited Responses**: Every answer includes source citations- 📎 **Cited Responses**: Every answer includes source citations

- 📄 **Document Support**: Upload PDFs, Word documents, and text files- 📄 **Document Support**: Upload PDFs, Word documents, and text files

- 💬 **Chat History**: Track all conversations- 💬 **Chat History**: Track all conversations

- 🔒 **User Authentication**: Secure login and data management- 🔒 **User Authentication**: Secure login and data management



## 🚀 Quick Start## 🚀 Quick Start



### Prerequisites### Prerequisites

- **Node.js** 18+ and npm- **Node.js** 18+ and npm

- **Python** 3.10+- **Python** 3.10+

- **PostgreSQL** 14+ (optional - can use Firebase)- **PostgreSQL** 14+ (optional - can use Firebase)

- **API Keys**: OpenAI, Pinecone (free tier)- **API Keys**: OpenAI, Pinecone (free tier)



### Installation (5 minutes)### Installation (5 minutes)



#### 1. Clone the Repository#### 1. Clone the Repository

```bash```bash

git clone https://github.com/maryem012/GREENY-RAG-Chatbot.gitgit clone https://github.com/maryem012/GREENY-RAG-Chatbot.git

cd GREENYcd GREENY

``````



#### 2. Setup Environment#### 2. Setup Environment

```bash```bash

# Copy environment template and fill in your API keys# Copy environment template and fill in your API keys

cp .env.example .envcp .env.example .env

# Edit .env with your credentials# Edit .env with your credentials

``````



#### 3. Start Backend (Terminal 1)#### 3. Start Backend (Terminal 1)

```bash```bash

cd backendcd backend

python -m venv venvpython -m venv venv

venv\Scripts\activate  # Windowsvenv\Scripts\activate  # Windows

source venv/bin/activate  # macOS/Linuxsource venv/bin/activate  # macOS/Linux



pip install -r requirements.txtpip install -r requirements.txt

python -m uvicorn app.main:app --reload --port 8000python -m uvicorn app.main:app --reload --port 8000

``````



#### 4. Start Frontend (Terminal 2)#### 4. Start Frontend (Terminal 2)

```bash```bash

cd frontendcd frontend

npm installnpm install

npm run devnpm run dev

``````



#### 5. Access the Application#### 5. Access the Application

- **Web App**: http://localhost:5173- **Web App**: http://localhost:5173

- **API Docs**: http://localhost:8000/docs- **API Docs**: http://localhost:8000/docs



## 📁 Project Structure## 📁 Project Structure



``````

GREENY/GREENY/

├── frontend/                           # React TypeScript web app├── frontend/                           # React TypeScript web app

│   ├── src/│   ├── src/

│   │   ├── components/                 # Reusable UI components│   │   ├── components/                 # Reusable UI components

│   │   ├── pages/│   │   ├── pages/

│   │   │   ├── ChatPage.tsx           # Main chat interface (redesigned)│   │   │   ├── ChatPage.tsx           # Main chat interface (redesigned)

│   │   │   ├── ProfilePage.tsx        # User greenhouse profile│   │   │   ├── ProfilePage.tsx        # User greenhouse profile

│   │   │   └── HistoryPage.tsx        # Chat history│   │   │   └── HistoryPage.tsx        # Chat history

│   │   ├── contexts/                   # Language & auth context│   │   ├── contexts/                   # Language & auth context

│   │   ├── hooks/                      # Custom React hooks│   │   ├── hooks/                      # Custom React hooks

│   │   ├── utils/│   │   ├── utils/

│   │   │   ├── languageDetection.ts   # Auto-detect Derja/French/English│   │   │   ├── languageDetection.ts   # Auto-detect Derja/French/English

│   │   │   └── translations.ts        # Multilingual UI text│   │   │   └── translations.ts        # Multilingual UI text

│   │   └── App.tsx│   │   └── App.tsx

│   ├── package.json│   ├── package.json

│   └── tsconfig.json│   └── tsconfig.json

││

├── backend/                            # FastAPI Python app├── backend/                            # FastAPI Python app

│   ├── app/│   ├── app/

│   │   ├── api/│   │   ├── api/

│   │   │   ├── chat.py                # Chat & RAG endpoints (with CRITICAL language enforcement)│   │   │   ├── chat.py                # Chat & RAG endpoints (with CRITICAL language enforcement)

│   │   │   ├── auth.py                # User authentication│   │   │   ├── auth.py                # User authentication

│   │   │   ├── documents.py           # Document upload & processing│   │   │   ├── documents.py           # Document upload & processing

│   │   │   └── profile.py             # Greenhouse profile management + check endpoint│   │   │   └── profile.py             # Greenhouse profile management + check endpoint

│   │   ├── config/│   │   ├── config/

│   │   │   └── settings.py            # Configuration management│   │   │   └── settings.py            # Configuration management

│   │   ├── schemas/│   │   ├── schemas/

│   │   │   └── schemas.py             # Pydantic data models│   │   │   └── schemas.py             # Pydantic data models

│   │   └── main.py                    # FastAPI app initialization│   │   └── main.py                    # FastAPI app initialization

│   ├── requirements.txt│   ├── requirements.txt

│   └── .env.example│   └── .env.example

││

├── database/                           # Database setup├── database/                           # Database setup

│   ├── migrations/                     # Alembic migration files│   ├── migrations/                     # Alembic migration files

│   └── schema.sql                      # Initial database schema│   └── schema.sql                      # Initial database schema

││

└── README.md└── README.md

``````



## 🛠 Technology Stack## 🛠 Technology Stack



### Frontend### Frontend

| Technology | Purpose || Technology | Purpose |

|-----------|---------||-----------|---------|

| **React 18** | UI framework || **React 18** | UI framework |

| **TypeScript** | Type-safe JavaScript || **TypeScript** | Type-safe JavaScript |

| **Tailwind CSS** | Responsive styling || **Tailwind CSS** | Responsive styling |

| **Axios** | HTTP client || **Axios** | HTTP client |

| **Vite** | Build tool & dev server || **Vite** | Build tool & dev server |



### Backend### Backend

| Technology | Purpose || Technology | Purpose |

|-----------|---------||-----------|---------|

| **FastAPI** | Web framework || **FastAPI** | Web framework |

| **Python 3.10+** | Programming language || **Python 3.10+** | Programming language |

| **Pydantic v2** | Data validation || **Pydantic v2** | Data validation |

| **Firebase** | User authentication & Firestore || **Firebase** | User authentication & Firestore |

| **OpenAI GPT** | AI responses (gpt-4-turbo-preview) || **OpenAI GPT** | AI responses (gpt-4-turbo-preview) |

| **Pinecone** | Vector embeddings (RAG) || **Pinecone** | Vector embeddings (RAG) |



### Infrastructure### Infrastructure

| Service | Purpose || Service | Purpose |

|---------|---------||---------|---------|

| **Firestore** | Real-time database & chat history || **Firestore** | Real-time database & chat history |

| **Pinecone** | Vector database for RAG retrieval || **Pinecone** | Vector database for RAG retrieval |

| **OpenAI API** | LLM for intelligent responses || **OpenAI API** | LLM for intelligent responses |



## 🔑 Environment Variables## 🔑 Environment Variables



Create `.env` in the project root:Create `.env` in the project root:



```env```env

# Backend - OpenAI# Backend - OpenAI

OPENAI_API_KEY=sk-...OPENAI_API_KEY=sk-...

OPENAI_MODEL=gpt-4-turbo-previewOPENAI_MODEL=gpt-4-turbo-preview

EMBEDDING_MODEL=text-embedding-3-smallEMBEDDING_MODEL=text-embedding-3-small



# Backend - Pinecone# Backend - Pinecone

PINECONE_API_KEY=...PINECONE_API_KEY=...

PINECONE_INDEX_NAME=agri-chatbotPINECONE_INDEX_NAME=agri-chatbot



# Backend - Firebase# Backend - Firebase

FIREBASE_DATABASE_ID=greeny-dbFIREBASE_DATABASE_ID=greeny-db

GOOGLE_APPLICATION_CREDENTIALS=path/to/credentials.jsonGOOGLE_APPLICATION_CREDENTIALS=path/to/credentials.json



# Backend - JWT# Backend - JWT

JWT_SECRET_KEY=your_super_secret_key_hereJWT_SECRET_KEY=your_super_secret_key_here



# Frontend# Frontend

VITE_API_URL=http://localhost:8000VITE_API_URL=http://localhost:8000



# System Configuration# System Configuration

SYSTEM_ROLE=agricultural expertSYSTEM_ROLE=agricultural expert

SYSTEM_SPECIALTY=greenhouse farming in TunisiaSYSTEM_SPECIALTY=greenhouse farming in Tunisia

SYSTEM_LOCATION=TunisiaSYSTEM_LOCATION=Tunisia

``````



## 📡 API Endpoints## 📡 API Endpoints



### Authentication### Authentication

```http```http

POST   /api/auth/register          # Create new user accountPOST   /api/auth/register          # Create new user account

POST   /api/auth/login             # User loginPOST   /api/auth/login             # User login

POST   /api/auth/logout            # User logoutPOST   /api/auth/logout            # User logout

``````



### Chat & RAG### Chat & RAG

```http```http

POST   /api/chat/message           # Send message (with RAG and language enforcement)POST   /api/chat/message           # Send message (with RAG and language enforcement)

GET    /api/chat/history/{user_id} # Get conversation historyGET    /api/chat/history/{user_id} # Get conversation history

``````



### Documents### Documents

```http```http

POST   /api/documents/upload       # Upload greenhouse documentPOST   /api/documents/upload       # Upload greenhouse document

GET    /api/documents/{user_id}    # List user documentsGET    /api/documents/{user_id}    # List user documents

DELETE /api/documents/{doc_id}     # Delete documentDELETE /api/documents/{doc_id}     # Delete document

``````



### Profile### Profile

```http```http

POST   /api/profile/greenhouse     # Create greenhouse profilePOST   /api/profile/greenhouse     # Create greenhouse profile

GET    /api/profile/greenhouse/{user_id}  # Get profileGET    /api/profile/greenhouse/{user_id}  # Get profile

PUT    /api/profile/greenhouse/{user_id}  # Update profilePUT    /api/profile/greenhouse/{user_id}  # Update profile

GET    /api/profile/check/{user_id}       # Check profile status with diagnosticsGET    /api/profile/check/{user_id}       # Check profile status with diagnostics

``````



## 💬 Supported Languages## 💬 Supported Languages



| Language | Script | Auto-Detect | Support Level || Language | Script | Auto-Detect | Support Level |

|----------|--------|-------------|----------------||----------|--------|-------------|----------------|

| **Tunisian Derja** | Arabic + Latin | Arabic script → 95% confidence | ⭐⭐⭐ Primary || **Tunisian Derja** | Arabic + Latin | Arabic script → 95% confidence | ⭐⭐⭐ Primary |

| **French** | Latin | French patterns → 90% confidence | ⭐⭐⭐ Full || **French** | Latin | French patterns → 90% confidence | ⭐⭐⭐ Full |

| **English** | Latin | English patterns → 90% confidence | ⭐⭐ Supported || **English** | Latin | English patterns → 90% confidence | ⭐⭐ Supported |



### Language System Architecture### Language System Architecture



**CRITICAL INSTRUCTIONS** in system prompt:**CRITICAL INSTRUCTIONS** in system prompt:

- Language enforcement with red flag emojis (🔴)- Language enforcement with red flag emojis (🔴)

- Absolute directives: "MUST respond ONLY in {language}"- Absolute directives: "MUST respond ONLY in {language}"

- Prohibition list: "DO NOT respond in Arabic, French, English..." per language- Prohibition list: "DO NOT respond in Arabic, French, English..." per language

- Profile inclusion marked as mandatory: "🔴 USER PROFILE (USE THIS IN YOUR RESPONSE):"- Profile inclusion marked as mandatory: "🔴 USER PROFILE (USE THIS IN YOUR RESPONSE):"



### Language-Specific Formatting### Language-Specific Formatting



**Tunisian Derja** 🇹🇳**Tunisian Derja** 🇹🇳

- Simple, colloquial language suitable for farmers- Simple, colloquial language suitable for farmers

- Structured format: Problem → Cause → Solution → Why → Action TODAY- Structured format: Problem → Cause → Solution → Why → Action TODAY

- Bullet points for lists- Bullet points for lists

- Agricultural terminology: خضرة (vegetables), طماطم (tomatoes), سقي (watering), سماد (fertilizer)- Agricultural terminology: خضرة (vegetables), طماطم (tomatoes), سقي (watering), سماد (fertilizer)

- Short sentences (max 2-3 lines)- Short sentences (max 2-3 lines)

- Distinctive Tunisian words: نتاع (ntaa3), نحوا (nhawwa), تعب (t3ab), قال (gal)- Distinctive Tunisian words: نتاع (ntaa3), نحوا (nhawwa), تعب (t3ab), قال (gal)



**French** 🇫🇷**French** 🇫🇷

- Professional, concise agricultural French- Professional, concise agricultural French

- Proper terminology for farming practices- Proper terminology for farming practices

- Structured response with clear headings- Structured response with clear headings

- Bullet points for organized information- Bullet points for organized information



**English** 🇬🇧**English** 🇬🇧

- Clear, professional English suitable for international farmers- Clear, professional English suitable for international farmers

- Practical, actionable advice with step-by-step guidance- Practical, actionable advice with step-by-step guidance

- Agricultural terminology and best practices- Agricultural terminology and best practices



## 🎨 Features## 🎨 Features



### 1. Intelligent Chat Interface### 1. Intelligent Chat Interface

- Real-time responses with citations showing document source- Real-time responses with citations showing document source

- Auto-language detection (Derja/French/English)- Auto-language detection (Derja/French/English)

- Message history with timestamps- Message history with timestamps

- Loading indicators with multilingual "Thinking..." text- Loading indicators with multilingual "Thinking..." text

- Copy, Save, and Delete actions on messages (appear on hover)- Copy, Save, and Delete actions on messages (appear on hover)

- Better typography and spacing for readability- Better typography and spacing for readability



### 2. Greenhouse Profile### 2. Greenhouse Profile

- Customizable greenhouse details (name, region, type, crops, irrigation type)- Customizable greenhouse details (name, region, type, crops, irrigation type)

- Personalized response generation based on profile- Personalized response generation based on profile

- Profile status checking endpoint with helpful diagnostics- Profile status checking endpoint with helpful diagnostics

- Profile validation with clear error messages- Profile validation with clear error messages

- Backward-compatible field name handling (greenhouse_type or type)- Backward-compatible field name handling (greenhouse_type or type)



### 3. Document Management### 3. Document Management

- Upload PDFs, Word docs, and text files- Upload PDFs, Word docs, and text files

- Automatic document processing and chunking (500 tokens with 50 token overlap)- Automatic document processing and chunking (500 tokens with 50 token overlap)

- Pinecone vector embedding for semantic search- Pinecone vector embedding for semantic search

- Citation tracking with document references- Citation tracking with document references

- Document validation and error handling- Document validation and error handling



### 4. RAG (Retrieval-Augmented Generation)### 4. RAG (Retrieval-Augmented Generation)

- Retrieves relevant documents from user's library using similarity search- Retrieves relevant documents from user's library using similarity search

- Combines user documents with global agricultural knowledge- Combines user documents with global agricultural knowledge

- Cites all sources in responses with document name, section, and page- Cites all sources in responses with document name, section, and page

- Similarity threshold: 0.35 for relevance filtering- Similarity threshold: 0.35 for relevance filtering

- Fallback to global knowledge when user documents insufficient- Fallback to global knowledge when user documents insufficient



### 5. Multi-language Chat### 5. Multi-language Chat

- **Derja** responses: Simple, understandable, action-oriented- **Derja** responses: Simple, understandable, action-oriented

- **French** responses: Professional, clear structure- **French** responses: Professional, clear structure

- **English** responses: Clear and practical guidance- **English** responses: Clear and practical guidance



### 6. Full-Screen Chat Panel### 6. Full-Screen Chat Panel

- Fixed layout that maintains consistent dimensions- Fixed layout that maintains consistent dimensions

- Uses `h-screen` and `min-h-0` flex constraints for proper sizing- Uses `h-screen` and `min-h-0` flex constraints for proper sizing

- Smooth scrolling with auto-scroll on new messages- Smooth scrolling with auto-scroll on new messages

- Responsive design for mobile and desktop- Responsive design for mobile and desktop



## 🧪 Testing## 🧪 Testing



### Backend Tests### Backend Tests

```bash```bash

cd backendcd backend

# Run all tests# Run all tests

pytest tests/ -vpytest tests/ -v



# Run specific test file# Run specific test file

pytest tests/test_chat.py -vpytest tests/test_chat.py -v



# Run with coverage# Run with coverage

pytest --cov=app tests/pytest --cov=app tests/

``````



### Frontend Tests### Frontend Tests

```bash```bash

cd frontendcd frontend

# Run tests# Run tests

npm run testnpm run test



# Run with coverage# Run with coverage

npm run test:coveragenpm run test:coverage

``````



## 📝 Development Workflow## 📝 Development Workflow



### Making Changes### Making Changes



1. **Create a feature branch**1. **Create a feature branch**

   ```bash   ```bash

   git checkout -b feature/your-feature-name   git checkout -b feature/your-feature-name

   ```   ```



2. **Make your changes** (follow project structure)2. **Make your changes** (follow project structure)



3. **Commit with clear messages** (Conventional Commits)3. **Commit with clear messages** (Conventional Commits)

   ```bash   ```bash

   git commit -m "feat: add new feature description"   git commit -m "feat: add new feature description"

   git commit -m "fix: resolve language enforcement issue"   git commit -m "fix: resolve language enforcement issue"

   git commit -m "docs: update README with profile check endpoint"   git commit -m "docs: update README with profile check endpoint"

   ```   ```



4. **Test your changes**4. **Test your changes**

   ```bash   ```bash

   # Backend tests   # Backend tests

   cd backend && pytest   cd backend && pytest

      

   # Frontend tests   # Frontend tests

   cd frontend && npm run test   cd frontend && npm run test

   ```   ```



5. **Push and create PR**5. **Push and create PR**

   ```bash   ```bash

   git push origin feature/your-feature-name   git push origin feature/your-feature-name

   ```   ```



### Code Style### Code Style

- **Backend**: Follow PEP 8 with Black formatter- **Backend**: Follow PEP 8 with Black formatter

- **Frontend**: ESLint + Prettier for TypeScript/React- **Frontend**: ESLint + Prettier for TypeScript/React

- **Commit Messages**: Conventional Commits format (feat:, fix:, docs:, etc.)- **Commit Messages**: Conventional Commits format (feat:, fix:, docs:, etc.)



## 🐛 Troubleshooting## 🐛 Troubleshooting



### Backend Issues### Backend Issues



**Profile Not Found Warning****Profile Not Found Warning**

- Check: Does user have a profile created?- Check: Does user have a profile created?

- Solution: Call `POST /api/profile/greenhouse` to create profile- Solution: Call `POST /api/profile/greenhouse` to create profile

- Check status: `GET /api/profile/check/{user_id}` for detailed diagnostics- Check status: `GET /api/profile/check/{user_id}` for detailed diagnostics

- Fields used: greenhouse_type (or legacy "type"), region, crops, irrigation_type- Fields used: greenhouse_type (or legacy "type"), region, crops, irrigation_type



**Language Always Responds in Derja/Arabic****Language Always Responds in Derja/Arabic**

- Check: Is `language` parameter in request? (should be "en", "fr", or "derja")- Check: Is `language` parameter in request? (should be "en", "fr", or "derja")

- Verify: Backend console shows correct language in system prompt- Verify: Backend console shows correct language in system prompt

- Verify: CRITICAL INSTRUCTIONS section shows language enforcement- Verify: CRITICAL INSTRUCTIONS section shows language enforcement

- Solution: Ensure request includes correct language field- Solution: Ensure request includes correct language field

- Clear: Backend caches - may need restart for changes- Clear: Backend caches - may need restart for changes



**English Responses Are Derja****English Responses Are Derja**

- Check: Language detection working? Run auto-detect test- Check: Language detection working? Run auto-detect test

- Check: Request explicitly includes `"language": "en"`- Check: Request explicitly includes `"language": "en"`

- Verify: English language instructions block exists in system prompt- Verify: English language instructions block exists in system prompt

- Solution: Explicitly set language to "en" in frontend- Solution: Explicitly set language to "en" in frontend



**Document Upload Fails****Document Upload Fails**

- Check: File size < 50MB- Check: File size < 50MB

- Check: Supported formats: PDF, DOCX, DOC, TXT- Check: Supported formats: PDF, DOCX, DOC, TXT

- Check: Pinecone connection and API key valid- Check: Pinecone connection and API key valid

- Check: Firestore has space for storing document metadata- Check: Firestore has space for storing document metadata



### Frontend Issues### Frontend Issues



**Chat Not Sending Messages****Chat Not Sending Messages**

- Check: Browser console for errors (F12 → Console tab)- Check: Browser console for errors (F12 → Console tab)

- Check: Backend is running on port 8000- Check: Backend is running on port 8000

- Check: VITE_API_URL in `.env` is correct- Check: VITE_API_URL in `.env` is correct

- Check: Network tab in DevTools for API response- Check: Network tab in DevTools for API response



**Language Switcher Not Working****Language Switcher Not Working**

- Hard refresh: Ctrl+Shift+R (or Cmd+Shift+R on Mac)- Hard refresh: Ctrl+Shift+R (or Cmd+Shift+R on Mac)

- Check: localStorage not disabled in browser- Check: localStorage not disabled in browser

- Check: LanguageContext provider wraps entire App component- Check: LanguageContext provider wraps entire App component

- Check: useLanguage hook is imported from correct context- Check: useLanguage hook is imported from correct context



**Chat Panel Height Shrinking****Chat Panel Height Shrinking**

- Solution: This issue has been fixed with `h-screen` and `min-h-0`- Solution: This issue has been fixed with `h-screen` and `min-h-0`

- If still occurs: Check that main container has `h-screen overflow-hidden`- If still occurs: Check that main container has `h-screen overflow-hidden`

- Check: Flex children have `min-h-0` constraint- Check: Flex children have `min-h-0` constraint



**Citations Not Showing****Citations Not Showing**

- Check: RAG retrieved documents from Pinecone- Check: RAG retrieved documents from Pinecone

- Check: OpenAI response includes citation metadata- Check: OpenAI response includes citation metadata

- Check: Frontend correctly parsing citation structure- Check: Frontend correctly parsing citation structure



## 📚 Documentation## 📚 Documentation



- **Language Detection**: See `frontend/src/utils/languageDetection.ts`- **Language Detection**: See `frontend/src/utils/languageDetection.ts`

- **System Prompt Architecture**: See `backend/app/api/chat.py` (CRITICAL INSTRUCTIONS section)- **System Prompt Architecture**: See `backend/app/api/chat.py` (CRITICAL INSTRUCTIONS section)

- **Language Enforcement**: See `backend/app/api/chat.py` (if/elif blocks for en, fr, derja)- **Language Enforcement**: See `backend/app/api/chat.py` (if/elif blocks for en, fr, derja)

- **RAG Implementation**: See `backend/app/api/chat.py` (`retrieve_relevant_documents` function)- **RAG Implementation**: See `backend/app/api/chat.py` (`retrieve_relevant_documents` function)

- **Profile Management**: See `backend/app/api/profile.py`- **Profile Management**: See `backend/app/api/profile.py`

- **Profile Check Endpoint**: See `backend/app/api/profile.py` (GET /api/profile/check/{user_id})- **Profile Check Endpoint**: See `backend/app/api/profile.py` (GET /api/profile/check/{user_id})



## 🚀 Deployment## 🚀 Deployment



### Local Development### Local Development

```bash```bash

# Backend# Backend

cd backendcd backend

python -m uvicorn app.main:app --reload --port 8000python -m uvicorn app.main:app --reload --port 8000



# Frontend# Frontend

cd frontendcd frontend

npm run devnpm run dev

``````



### Production Build### Production Build

```bash```bash

# Frontend# Frontend

cd frontendcd frontend

npm run buildnpm run build

# Output: dist/ folder ready for static hosting# Output: dist/ folder ready for static hosting



# Backend# Backend

# Deploy to: Railway, Heroku, AWS, Google Cloud, etc.# Deploy to: Railway, Heroku, AWS, Google Cloud, etc.

# Use Gunicorn for WSGI server:# Use Gunicorn for WSGI server:

pip install gunicornpip install gunicorn

gunicorn app.main:app -w 4 -b 0.0.0.0:8000gunicorn app.main:app -w 4 -b 0.0.0.0:8000

``````



### Docker Deployment### Docker Deployment

```bash```bash

# Build and run with Docker Compose# Build and run with Docker Compose

docker-compose up -ddocker-compose up -d



# Stop containers# Stop containers

docker-compose downdocker-compose down

``````



### Environment Setup for Production### Environment Setup for Production

1. Set strong JWT_SECRET_KEY1. Set strong JWT_SECRET_KEY

2. Use PostgreSQL instead of SQLite2. Use PostgreSQL instead of SQLite

3. Enable HTTPS/SSL3. Enable HTTPS/SSL

4. Set CORS origins correctly4. Set CORS origins correctly

5. Use environment-specific .env files5. Use environment-specific .env files



## 🤝 Contributing## 🤝 Contributing



We welcome contributions! Please:We welcome contributions! Please:



1. Fork the repository1. Fork the repository

2. Create a feature branch: `git checkout -b feature/your-feature`2. Create a feature branch: `git checkout -b feature/your-feature`

3. Make your changes following project structure3. Make your changes following project structure

4. Write/update tests if applicable4. Write/update tests if applicable

5. Commit with clear messages: `git commit -m "feat: add feature"`5. Commit with clear messages: `git commit -m "feat: add feature"`

6. Submit a pull request with description6. Submit a pull request with description



## 📜 License## 📜 License



This project is licensed under the MIT License - see the LICENSE file for details.This project is licensed under the MIT License - see the LICENSE file for details.



## 👥 Team & Contact## 👥 Team & Contact



- **Developer**: Maryem Benayed- **Developer**: Maryem Benayed

- **Project**: GREENY RAG Chatbot for Tunisian Greenhouse Farmers- **Project**: GREENY RAG Chatbot for Tunisian Greenhouse Farmers

- 📧 **Email**: maryem.benayed@example.com- 📧 **Email**: maryem.benayed@example.com

- 🐛 **Issues**: [GitHub Issues](https://github.com/maryem012/GREENY-RAG-Chatbot/issues)- 🐛 **Issues**: [GitHub Issues](https://github.com/maryem012/GREENY-RAG-Chatbot/issues)

- 💬 **Discussions**: [GitHub Discussions](https://github.com/maryem012/GREENY-RAG-Chatbot/discussions)- 💬 **Discussions**: [GitHub Discussions](https://github.com/maryem012/GREENY-RAG-Chatbot/discussions)



## 🙏 Acknowledgments## 🙏 Acknowledgments



- **OpenAI** for GPT API and embeddings- **OpenAI** for GPT API and embeddings

- **Pinecone** for vector database- **Pinecone** for vector database

- **Firebase** for authentication and real-time database- **Firebase** for authentication and real-time database

- **Tunisian agricultural experts** for domain knowledge and feedback- **Tunisian agricultural experts** for domain knowledge and feedback

- **React and FastAPI communities** for excellent frameworks- **React and FastAPI communities** for excellent frameworks



## 🎯 Roadmap## 🎯 Roadmap



- [ ] Voice input support (Derja/French)- [ ] Voice input support (Derja/French)

- [ ] Real-time weather integration (alerts and recommendations)- [ ] Real-time weather integration (alerts and recommendations)

- [ ] Crop yield prediction with ML models- [ ] Crop yield prediction with ML models

- [ ] Satellite imagery analysis (NDVI for crop health)- [ ] Satellite imagery analysis (NDVI for crop health)

- [ ] Cooperative greenhouse mode (shared profiles)- [ ] Cooperative greenhouse mode (shared profiles)

- [ ] Compliance and certification assistant- [ ] Compliance and certification assistant

- [ ] Long-term AI advisor with seasonal planning- [ ] Long-term AI advisor with seasonal planning

- [ ] Advanced analytics dashboard with insights- [ ] Advanced analytics dashboard with insights

- [ ] Mobile app (React Native)- [ ] Mobile app (React Native)

- [ ] Video tutorials in Tunisian Derja- [ ] Video tutorials in Tunisian Derja



## 📊 Recent Improvements## 📊 Recent Improvements



### v1.1 - Language Enforcement & UI Polish### v1.1 - Language Enforcement & UI Polish

- ✅ Added CRITICAL INSTRUCTIONS section with absolute language enforcement- ✅ Added CRITICAL INSTRUCTIONS section with absolute language enforcement

- ✅ Redesigned ChatPage.tsx with professional UI styling- ✅ Redesigned ChatPage.tsx with professional UI styling

- ✅ Fixed chat panel height with proper flex constraints- ✅ Fixed chat panel height with proper flex constraints

- ✅ Added English language-specific instructions- ✅ Added English language-specific instructions

- ✅ Enhanced Derja response quality with structured format- ✅ Enhanced Derja response quality with structured format

- ✅ Added profile check endpoint with diagnostics- ✅ Added profile check endpoint with diagnostics

- ✅ Improved error messages and logging- ✅ Improved error messages and logging



### v1.0 - Initial Release### v1.0 - Initial Release

- ✅ Core RAG functionality with Pinecone- ✅ Core RAG functionality with Pinecone

- ✅ Multi-language support (Derja, French)- ✅ Multi-language support (Derja, French)

- ✅ Document upload and processing- ✅ Document upload and processing

- ✅ Chat history tracking- ✅ Chat history tracking

- ✅ User authentication- ✅ User authentication

- ✅ Greenhouse profile customization- ✅ Greenhouse profile customization



------



<div align="center"><div align="center">



**Made with 🌾 for Tunisia's greenhouse farmers****Made with 🌾 for Tunisia's greenhouse farmers**



If this project helps you, please give it a ⭐ on GitHub!If this project helps you, please give it a ⭐ on GitHub!



[Report a Bug](https://github.com/maryem012/GREENY-RAG-Chatbot/issues) • [Request a Feature](https://github.com/maryem012/GREENY-RAG-Chatbot/discussions) • [View Documentation](https://github.com/maryem012/GREENY-RAG-Chatbot/wiki)[Report a Bug](https://github.com/maryem012/GREENY-RAG-Chatbot/issues) • [Request a Feature](https://github.com/maryem012/GREENY-RAG-Chatbot/discussions) • [View Documentation](https://github.com/maryem012/GREENY-RAG-Chatbot/wiki)



</div></div>

