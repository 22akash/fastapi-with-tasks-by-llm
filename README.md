# fastapi-with-tasks-by-llm


## Overview
This project is a FastAPI-based service that provides various data processing capabilities powered by AI. It offers a collection of tools for handling different types of data operations, from text processing to file management, all accessible through a simple REST API.

## Features

### Core Functionalities
- **Contact Management**: Sort and organize contact information
- **Log Processing**: Handle and analyze log files
- **Markdown Processing**: 
  - Generate indexes for markdown files
  - Convert markdown to HTML
  - Format markdown using Prettier
- **Date Processing**: Analyze and count specific days from date collections
- **Email Processing**: Extract sender information from email content
- **Sales Analysis**: Calculate sales metrics from SQLite databases
- **Text Analysis**: Find similar comments using AI embeddings
- **Web Scraping**: Extract content from websites
- **CSV Processing**: Convert CSV files to JSON format
- **Data Generation**: Setup and run data generation scripts

### Technical Features
- RESTful API endpoints
- CORS support
- Error handling and validation
- AI-powered text processing using GPT models
- File system operations
- Database interactions
- Web scraping capabilities

## Installation

### Prerequisites
- Python 3.8+
- Node.js (for Prettier formatting)
- pip (Python package manager)

### Setup
1. Clone the repository:
```bash
git clone [repository-url]
cd [repository-name]
```

2. Create and activate a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
npm install prettier@3.4.2 -g
```

4. Set up environment variables:
```bash
export AIPROXY_TOKEN=your_token_here
```

## Usage

### Starting the Server
```bash
uvicorn main:app --reload
```

### API Endpoints

#### POST /run
Execute a data processing task.
```bash
curl -X POST "http://localhost:8000/run" -H "Content-Type: application/json" -d '{"task": "your task description"}'
```

#### GET /run
Alternative endpoint for task execution using query parameters.
```bash
curl "http://localhost:8000/run?task=your%20task%20description"
```

#### GET /read
Read file contents.
```bash
curl "http://localhost:8000/read?path=path/to/file"
```

### Example Tasks

1. Sort Contacts:
```json
{
    "task": "Sort the contacts in data/contacts.json"
}
```

2. Process Log Files:
```json
{
    "task": "Extract recent log entries from data/logs/"
}
```

3. Convert Markdown to HTML:
```json
{
    "task": "Convert markdown file data/docs/example.md to HTML"
}
```

## Security Considerations
- The API includes safeguards against accessing files outside the /data directory
- File deletion operations are restricted
- CORS is configured for specific origins
- API token validation is implemented

## Error Handling
The API provides detailed error messages for:
- File not found errors
- Invalid input formats
- Processing errors
- API communication errors
- Authentication errors

## Contributing
1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License
[Add your license information here]

## Support
For support, please [create an issue](link-to-issues) in the repository.

## Authors
[Add author information here]

## Acknowledgments
- OpenAI for GPT integration
- FastAPI framework
- Beautiful Soup for web scraping
- Pandas for data processing
