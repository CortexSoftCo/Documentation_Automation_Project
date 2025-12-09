
# Documentation Automation Project

<img width="1589" height="678" alt="Github_Workflow" src="https://github.com/user-attachments/assets/494da025-4ee7-4a05-9bca-6999d400a361" />




**Automated document generation powered by voice or text commands**

## Security Notice


**This workflow contains placeholder values for API credentials.** Before importing into N8N:

1. Replace all `YOUR_*_HERE` placeholders with your actual credentials.
2. Use N8N's credential management system instead of hardcoding values.
3. Do not commit files containing real API keys or tokens.
4. Review the `.env.example` file for required credentials.

## Overview

This project is an intelligent documentation automation system that enables users to create documents ranging from 10 to 200 pages through voice or text commands. It leverages AI to brainstorm, structure, and generate complete documents with embedded media, storing them in a modular format on GitHub.

## Key Features

### Intelligent Document Generation
- Voice & text input
- AI-powered brainstorming and outline generation
- Outline approval workflow
- Scalable output (10–200+ pages)

### Media Integration
- Automatic image insertion
- SVG graphics generation
- Charts and visualizations
- Organized asset management

### Dynamic Document Management
- Section-wise modular structure
- Real-time editing
- GitHub-based version control
- Structured asset storage

### Context-Aware Intelligence
- Vector database for semantic search (Pinecone)
- Reference and query previous documents
- Context-aware content retrieval
- Knowledge base of generated documents

## Technology Stack

| Category | Technologies |
|----------|-------------|
| Workflow Automation | N8N |
| AI & Language Models | OpenAI API, Claude API |
| Document Processing | Google Docs API, Google Drive API |
| Communication | Telegram API |
| Vector Database | Pinecone |
| Version Control | GitHub API |
| Database | Supabase |
| Project Management | Notion |

## System Architecture

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

## How It Works

1. **Document Request** – User sends a command via Telegram specifying requirements.
2. **AI Brainstorming** – Generates outline using AI and context from the vector database.
3. **Outline Approval** – User reviews and approves the outline.
4. **Document Generation** – Full document is generated with embedded images, charts, and SVGs.
5. **Asset Management** – Organized structure:
```
repository/
├── document-name/
│   ├── sections/
│   ├── assets/
│   └── document-metadata.json
```
6. **GitHub Upload** – Document and assets committed to GitHub.
7. **Vector Database Update** – Indexed for future queries and context.

## Use Cases

- Technical documentation: API docs, user guides
- Research reports with visualizations
- Business documents: proposals, reports, strategic plans
- Educational content: tutorials, study guides
- Project documentation: README files, architecture docs

## Setup & Configuration

### Prerequisites
- N8N instance (self-hosted or cloud)
- API keys for OpenAI/Claude, Google Cloud, Telegram Bot, Pinecone, GitHub, Supabase

### Installation
1. Clone the repository:
```bash
git clone <repository-url>
cd documentation-automation-project
```
2. Import N8N workflow and configure credentials.
3. Set environment variables:
```
TELEGRAM_BOT_TOKEN
OPENAI_API_KEY / CLAUDE_API_KEY
PINECONE_API_KEY
GITHUB_TOKEN
SUPABASE_URL / SUPABASE_KEY
```
4. Initialize Pinecone vector database.
5. Enable and test the workflow.

## Usage

**Create a Document:**
```
/create document about "Machine Learning Fundamentals" - Target: 50 pages
```

**Approve or Modify Outline:**
```
/approve
/modify Add section about neural networks
```

**Edit a Section:**
```
/edit document-name section-3 Update section content
```

**Query Documents:**
```
/query What documents exist about machine learning?
```

## Features Roadmap

- Multi-language support
- Custom templates
- Collaborative editing
- Export to PDF, DOCX, LaTeX
- Advanced visualization options
- Citation management

## Contributing

Contributions are welcome. Submit pull requests or open issues for bugs and feature requests.

## License

[Specify your license here]

## Authors

**Umair** – Initial work

## Acknowledgments

- N8N community
- OpenAI and Anthropic
- Open-source contributors

## Support

- Open an issue in the repository
- Contact via [your contact method]
