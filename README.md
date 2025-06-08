# AI-Based Railway Grievance Resolution Portal

## Overview
An intelligent web application designed to streamline railway complaint management using machine learning and AI technologies. The system automatically categorizes complaints, predicts urgency levels, and provides real-time assistance through an AI chatbot.

## Features

### 🤖 AI-Powered Functionality
- **Automatic Department Classification**: ML model categorizes complaints into appropriate railway departments
- **Urgency Prediction**: Advanced stacking model predicts complaint urgency (Low/Medium/High) using TF-IDF and numerical features
- **Sentiment Analysis**: Real-time sentiment analysis of user feedback using TextBlob
- **AI Chatbot**: Rail Sahayak - An intelligent assistant powered by Ollama's TinyLLama model

### 👥 Multi-Role System
- **Users**: Submit complaints, track status, provide feedback
- **Employees**: Manage assigned complaints, mark as resolved
- **Admins**: Department-wise dashboard, employee management, analytics

### 📊 Analytics & Insights
- Real-time complaint tracking and status updates
- Sentiment analysis dashboard with visual charts
- Employee performance metrics
- Feedback trend analysis over time
- Department-wise statistics and reporting

### 🔧 Technical Features
- Real-time messaging with SocketIO
- Secure file upload for complaint evidence
- Automated employee assignment based on workload
- Database migration support with Flask-Migrate

## Technology Stack

### Backend
- **Flask**: Web framework
- **SQLAlchemy**: Database ORM
- **Flask-Login**: User authentication
- **Flask-SocketIO**: Real-time communication

### Machine Learning
- **scikit-learn**: ML model training and prediction
- **TextBlob**: Natural language processing
- **TF-IDF Vectorization**: Text feature extraction
- **Stacking Classifier**: Ensemble learning for urgency prediction

### AI Integration
- **LangChain**: AI workflow orchestration
- **Ollama**: Local LLM deployment
- **TinyLLama**: Lightweight language model

### Frontend
- **HTML/CSS/JavaScript**: User interface
- **Chart.js**: Data visualization
- **Bootstrap**: Responsive design

### Database
- **SQLite**: Development database
- **Flask-Migrate**: Database version control

## Installation

### Prerequisites
```bash
Python 3.8+
pip
```

### Setup
```bash
git clone https://github.com/NishantBide/AI-Based-Railway-Grievance-Resolution-Portal.git
cd AI-Based-Railway-Grievance-Resolution-Portal
```

```bash
pip install -r requirements.txt
```

```bash
flask db init
flask db migrate -m "Initial migration"
flask db upgrade
```

### Environment Configuration
Create a `.env` file:
```env
LANGCHAIN_TRACING_V2=true
LANGCHAIN_API_KEY=your_langchain_api_key
SECRET_KEY=your_secret_key
```

### Model Files
Ensure the following ML model files are present in `project-model-pickle-files/`:
- Department classifier models
- Urgency prediction models
- TF-IDF vectorizers
- Label encoders

## Usage

### Start the Application
```bash
python app.py
```

### Access the Portal
- Navigate to `http://localhost:5000`
- Register as User/Employee/Admin
- Start submitting and managing complaints

### User Workflow
1. **Register/Login** - Create account or sign in
2. **Submit Complaint** - Describe issue with optional file attachments
3. **Track Status** - Monitor complaint progress in real-time
4. **Provide Feedback** - Rate and review resolution quality
5. **Chat Support** - Get instant help from Rail Sahayak AI

### Admin Features
- View department-specific complaints
- Monitor employee performance
- Analyze sentiment trends
- Generate statistical reports

## Project Structure

```
├── app.py                          # Main application file
├── models.py                       # Database models
├── templates/                      # HTML templates
├── static/                         # CSS, JS, images
├── project-model-pickle-files/     # ML model files
│   ├── department-classifier/
│   └── urgency-predict/
├── uploads/                        # User uploaded files
├── conversation_history.json       # Chatbot conversation log
└── requirements.txt               # Python dependencies
```

## Machine Learning Models

### Department Classification
- **Algorithm**: TF-IDF + Classification model
- **Purpose**: Auto-categorize complaints into railway departments
- **Departments**: Safety, Medical, Cleaning, Food Services, etc.

### Urgency Prediction
- **Algorithm**: Stacking Classifier with TF-IDF and numerical features
- **Features**: Text length, word count, sentiment polarity
- **Output**: Low/Medium/High urgency levels

## API Endpoints

### Authentication
- `POST /login` - User authentication
- `POST /register` - User registration
- `GET /logout` - User logout

### Complaints
- `GET /complaint` - Complaint submission form
- `POST /complaint` - Submit new complaint
- `GET /track_complaints` - View complaint status

### Feedback
- `POST /submit_feedback/<complaint_id>` - Submit feedback
- `GET /admin_dashboard/<department>` - Admin analytics

### Chatbot
- `GET /chatbot` - Chat interface
- `POST /send_message` - Send message to AI

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Indian Railways for inspiration
- Ollama team for local LLM deployment
- LangChain community for AI integration tools
- Flask community for web framework support

## Contact

**Nishant Bide** - [GitHub Profile](https://github.com/NishantBide)

Project Link: [https://github.com/NishantBide/AI-Based-Railway-Grievance-Resolution-Portal](https://github.com/NishantBide/AI-Based-Railway-Grievance-Resolution-Portal)

---

*Built with ❤️ for better railway services*
