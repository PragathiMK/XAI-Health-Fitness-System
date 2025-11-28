# GitHub Setup Instructions

## 🚀 Quick Setup After Cloning

### Step 1: Clone the Repository
```bash
git clone https://github.com/YOUR_USERNAME/health_fitness_xai.git
cd health_fitness_xai
```

### Step 2: Set Up Environment Variables
```bash
# Copy the example file
cp .env.example .env

# Edit .env with your actual credentials
# You'll need:
# - Firebase credentials (from Firebase Console)
# - Google Gemini API key (from Google Cloud Console)
```

### Step 3: Install Dependencies
```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Install requirements
pip install -r requirements.txt
```

### Step 4: Set Up Firebase
1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Create a new project or select existing
3. Enable Firebase Authentication (Email/Password)
4. Enable Firebase Realtime Database
5. Download service account credentials
6. Save as `firebase_credentials.json` in project root

### Step 5: Configure Firebase Database Rules
1. Go to Realtime Database → Rules
2. Replace with:
```json
{
  "rules": {
    ".read": true,
    ".write": true
  }
}
```
3. Click Publish

### Step 6: Run the Application
```bash
python app.py
```

Open browser to: http://localhost:5000

---

## 📋 Important Files

**DO NOT COMMIT:**
- `.env` - Contains sensitive credentials
- `firebase_credentials.json` - Service account credentials
- `__pycache__/` - Python cache files
- `venv/` - Virtual environment

**These are already in `.gitignore`** ✅

**DO COMMIT:**
- `.env.example` - Template for environment variables
- `requirements.txt` - Python dependencies
- All source code files
- Documentation files
- Configuration files

---

## 🔐 Security Checklist

Before pushing to GitHub:

✅ `.env` file is in `.gitignore`  
✅ `firebase_credentials.json` is in `.gitignore`  
✅ No API keys in source code  
✅ No passwords in documentation  
✅ `.env.example` provided as template  
✅ README has setup instructions  

---

## 📚 Documentation Files

- **README.md** - Main documentation
- **QUICK_START_GUIDE.md** - Quick setup guide
- **PROJECT_SUMMARY.md** - Project overview and architecture
- **SECURITY_GUIDE.md** - Security best practices
- **.env.example** - Environment variables template

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

---

## 📝 License

Add your license information here (MIT, Apache, etc.)

**Happy coding!** 🚀
