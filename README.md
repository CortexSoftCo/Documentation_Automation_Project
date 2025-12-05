# Documentation Automation Project

> **Automated document generation powered by voice or text commands**

## ⚠️ Security Notice

**This workflow contains placeholder values for API credentials.** Before importing into N8N:
1. Replace all `YOUR_*_HERE` placeholders with your actual credentials
2. Use N8N's credential management system instead of hardcoding values
3. Never commit files containing real API keys or tokens
4. Review the `.env.example` file for required credentials

## 🎯 Overview

This project is an intelligent documentation automation system that allows users to create comprehensive documents ranging from 10 to 200 pages through simple voice or text commands. The system leverages AI to brainstorm, structure, and generate complete documents with embedded media, storing them in a modular format on GitHub.

## ✨ Key Features

### 🤖 Intelligent Document Generation
- **Voice & Text Input**: Create documents using natural language commands
- **Smart Outlining**: AI-powered brainstorming and outline generation
- **Approval Workflow**: Review and approve outlines before full document generation
- **Scalable Output**: Generate documents from 10 to 200+ pages based on requirements

### 📊 Rich Media Integration
- **Automatic Image Insertion**: Relevant images added contextually
- **SVG Graphics**: Custom vector graphics generation
- **Charts & Visualizations**: Data-driven charts and diagrams
- **Asset Management**: All media stored alongside document sections

### 🔄 Dynamic Document Management
- **Modular Structure**: Documents stored section-by-section for easy management
- **Real-time Editing**: Request changes to any section and get instant updates
- **Version Control**: GitHub-based storage ensures complete revision history
- **Organized Assets**: SVGs, images, and visualizations stored systematically

### 🧠 Context-Aware Intelligence
- **Vector Database**: Pinecone-powered semantic search across all documents
- **Historical Context**: Reference and query previous documents
- **Smart Retrieval**: High-accuracy answers about past and current documents
- **Knowledge Base**: Build an evolving repository of generated content

## 🛠️ Technology Stack

| Category | Technologies |
|----------|-------------|
| **Workflow Automation** | N8N |
| **AI & Language Models** | OpenAI API, Claude API |
| **Document Processing** | Google Docs API, Google Drive API |
| **Communication** | Telegram API (Bot Interface) |
| **Vector Database** | Pinecone |
| **Version Control** | GitHub API |
| **Database** | Supabase |
| **Project Management** | Notion |

## 🏗️ System Architecture

```
User Input (Voice/Text via Telegram)
           ↓
    N8N Workflow Engine
           ↓
    ┌──────┴──────┐
    ↓             ↓
AI Outlining   Vector DB Query
(OpenAI/Claude)  (Pinecone)
    ↓             ↓
Approval Gate    Context Retrieval
    ↓
Document Generation
    ↓
Media Generation & Integration
(Images, SVGs, Charts)
    ↓
Modular Storage Structure
    ↓
GitHub Repository Upload
    ↓
Metadata → Supabase
```

## 📋 How It Works

### 1. **Document Request**
User sends a voice or text command via Telegram specifying the document requirements.

### 2. **AI Brainstorming**
The system uses AI (OpenAI/Claude) to:
- Analyze the request
- Research relevant context from the vector database
- Generate a comprehensive outline

### 3. **Outline Approval**
The proposed outline is sent to the user for review and approval.

### 4. **Document Generation**
Once approved, the system:
- Generates full content for each section
- Creates relevant images, SVGs, and charts
- Structures content in modular sections

### 5. **Asset Management**
All generated assets are organized:
```
repository/
├── document-name/
│   ├── sections/
│   │   ├── 01-introduction.md
│   │   ├── 02-overview.md
│   │   └── ...
│   ├── assets/
│   │   ├── images/
│   │   ├── svgs/
│   │   └── charts/
│   └── document-metadata.json
```

### 6. **GitHub Upload**
Complete document with all assets is committed to GitHub repository.

### 7. **Vector Database Update**
Document content is indexed in Pinecone for future reference and queries.

## 🚀 Use Cases

- **Technical Documentation**: API docs, user guides, system documentation
- **Research Reports**: Comprehensive research papers with data visualization
- **Business Documents**: Proposals, reports, strategic plans
- **Educational Content**: Course materials, tutorials, study guides
- **Project Documentation**: README files, project specs, architecture docs

## 🔧 Setup & Configuration

### Prerequisites
- N8N instance (self-hosted or cloud)
- API keys for:
  - OpenAI or Claude
  - Google Cloud (Docs & Drive APIs)
  - Telegram Bot Token
  - Pinecone
  - GitHub Personal Access Token
  - Supabase credentials

### Installation Steps

1. **Clone the Repository**
   ```bash
   git clone <repository-url>
   cd documentation-automation-project
   ```

2. **Import N8N Workflow**
   - Open N8N
   - Import `Documentation_Automation_Project.json`
   - Configure credentials for all services

3. **Configure API Credentials**
   Set up credentials in N8N for:
   - OpenAI/Claude API
   - Google APIs (OAuth2)
   - Telegram Bot
   - Pinecone API
   - GitHub API
   - Supabase connection

4. **Set Environment Variables**
   Configure the following in your N8N environment:
   - `TELEGRAM_BOT_TOKEN`
   - `OPENAI_API_KEY` / `CLAUDE_API_KEY`
   - `PINECONE_API_KEY`
   - `GITHUB_TOKEN`
   - `SUPABASE_URL` and `SUPABASE_KEY`

5. **Initialize Vector Database**
   - Create Pinecone index with appropriate dimensions
   - Configure index name in workflow

6. **Activate Workflow**
   - Enable the N8N workflow
   - Test with a sample document request

## 💬 Usage

### Creating a Document

1. **Send Command to Telegram Bot**
   ```
   /create document about "Machine Learning Fundamentals" 
   - Target: 50 pages
   - Include: diagrams, code examples, and case studies
   ```

2. **Review Outline**
   The bot will send a structured outline for your approval.

3. **Approve or Request Changes**
   ```
   /approve
   ```
   or
   ```
   /modify Add section about neural networks
   ```

4. **Receive Document**
   Once generated, you'll receive:
   - GitHub repository link
   - Google Docs link (if configured)
   - Summary of generated content

### Editing a Section

```
/edit document-name section-3
Update the section to include more recent research from 2024
```

### Querying Documents

```
/query What documents do I have about machine learning?
```

## 📊 Features Roadmap

- [ ] Multi-language document generation
- [ ] Custom template support
- [ ] Collaborative editing
- [ ] Export to multiple formats (PDF, DOCX, LaTeX)
- [ ] Advanced visualization options
- [ ] Citation management
- [ ] Voice-to-document direct generation

## 🤝 Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues for bugs and feature requests.

## 📄 License

[Specify your license here]

## 👥 Authors

**Umair** - *Initial work*

## 🙏 Acknowledgments

- N8N community for workflow automation
- OpenAI and Anthropic for AI capabilities
- All open-source contributors

## 📞 Support

For questions or support, please:
- Open an issue in the repository
- Contact via [your contact method]

---

**Built with ❤️ using N8N and AI**
