# Health & Fitness XAI System

**Version:** 1.0 | **Status:** ✅ Production Ready | **Last Updated:** November 2025

## Overview
An advanced health and fitness recommendation system that uses **Explainable Artificial Intelligence (XAI)** to provide personalized diet and exercise plans with clear, understandable explanations. Features Firebase cloud integration, AI-powered recommendations via Google Gemini, and comprehensive daily activity tracking.

## 🔨 Development Methodology

### How We Built This Project

**1. Requirements Analysis & Planning**
- Identified 3 core objectives: Data Collection, XAI Recommendations, Clear Explanations
- Defined user personas (Regular users, Admin users)
- Planned feature set and system capabilities
- Created detailed requirement specifications

**2. System Architecture Design**
- Designed layered architecture (5 layers: Client, Application, Business Logic, Data, External Services)
- Created system diagrams for visualization
- Defined data models and database schema
- Planned API endpoints and routes

**3. Backend Development (Python + Flask)**
- Built Flask web server with routing system
- Implemented Firebase authentication module
- Developed health metrics calculation engine:
  - BMI calculation
  - BMR (Basal Metabolic Rate) using Mifflin-St Jeor formula
  - TDEE (Total Daily Energy Expenditure) calculation
- Created recommendation engines:
  - Diet Engine: Calorie targets, macronutrient distribution, meal planning
  - Exercise Engine: Workout splits, exercise selection, duration planning
- Integrated Google Gemini API for personalized AI recommendations
- Built daily activity tracking system
- Implemented feedback collection system

**4. XAI (Explainable AI) Implementation**
- Implemented feature importance analysis to show which factors matter most
- Created decision factors module to explain WHY recommendations were made
- Built transparent calculation display showing all formulas and steps
- Developed confidence scoring for all predictions
- Integrated SHAP explainer for advanced machine learning interpretability

**5. Frontend Development (HTML/CSS/JavaScript)**
- Created responsive web interface
- Built authentication pages (Login, Signup)
- Developed profile creation form with validation
- Created dashboard with 4 tabs:
  - Overview: Key metrics and goals
  - Diet Plan: Calories, macros, meal plans
  - Exercise Plan: Weekly schedule and exercises
  - Why This Works: XAI explanations
- Implemented daily tracker interface
- Built admin dashboard for user management
- Designed mobile-responsive styling

**6. Database & Cloud Integration**
- Integrated Firebase Authentication for secure user management
- Set up Firebase Realtime Database for cloud storage
- Implemented real-time data synchronization
- Created database schema with proper relationships
- Built data persistence layer

**7. API Development**
- Created 20+ REST API endpoints
- Implemented authentication middleware
- Built request validation system
- Developed comprehensive error handling
- Created JSON response formatting
- Implemented data export functionality

**8. Testing & Optimization**
- Tested authentication flow (signup, login, logout)
- Validated health metrics calculations
- Tested recommendation generation accuracy
- Verified XAI explanations are clear and accurate
- Optimized database queries
- Tested Firebase integration
- Achieved ~500ms page load time

**9. Documentation**
- Created comprehensive README with all details
- Documented all 20+ API endpoints
- Wrote installation and setup guide
- Created configuration instructions
- Documented technology stack
- Created system architecture diagrams
- Added methodology flowchart for presentations and reports

### Key Development Principles Used
- **User-Centric Design:** Focus on what users need to understand
- **Scientific Accuracy:** Based on proven health formulas (BMI, BMR, TDEE)
- **Transparency:** Every recommendation includes clear reasoning
- **Scalability:** Cloud-based architecture ready for growth
- **Security:** Firebase authentication and encrypted data
- **Iterative Development:** Build, test, optimize, document

## ✨ Key Features

### ✅ Cloud Integration & Storage
- **Firebase Authentication:** Secure email/password authentication
- **Realtime Database:** Cloud-based user profiles, tracker data, and feedback
- **Real-time Sync:** Instant data synchronization across devices using REST API
- **Cloud Security:** Encrypted data at rest and in transit
- **Automatic Data Persistence:** Profile, tracker, and feedback data automatically saved to Firebase

### ✅ AI-Powered Features
- **Google Gemini API:** Natural language AI recommendations
- **SHAP Explainer:** Advanced machine learning interpretability
- **Personalized Advice:** Context-aware health recommendations
- **Confidence Scoring:** Reliability indicators for all suggestions

### ✅ Objective 1: User Data Collection & Management
- Comprehensive user profile system collecting:
  - Basic metrics: Age, weight, height, gender
  - Activity level assessment
  - Fitness goals (weight loss, muscle gain, maintenance, endurance)
  - Dietary restrictions and medical conditions
- Automatic calculation of:
  - BMI (Body Mass Index)
  - BMR (Basal Metabolic Rate using Mifflin-St Jeor Equation)
  - TDEE (Total Daily Energy Expenditure)

### ✅ Objective 2: XAI-Based Recommendation System
- **Diet Recommendations:**
  - Personalized calorie targets based on goals
  - Optimized macronutrient distribution (protein, carbs, fats)
  - Sample meal plans with specific food items and quantities
  - Clear explanations for every recommendation

- **Exercise Recommendations:**
  - Customized workout splits (cardio, strength, flexibility)
  - Weekly workout plans with specific exercises
  - Sets, reps, and duration for each exercise
  - Expected calorie burn calculations

### ✅ Objective 3: Clear & Understandable Explanations
- **XAI Techniques Implemented:**
  - Feature importance visualization
  - Decision factor analysis
  - Step-by-step reasoning for recommendations
  - Outcome predictions with confidence levels

- **Transparency Features:**
  - Why each calorie target was chosen
  - How activity level affects recommendations
  - Impact of each user characteristic on the plan
  - Scientific basis for calculations (BMR formulas, etc.)

### ✅ Additional Features
- **Daily Activity Tracking:** Log steps, water intake, sleep hours, meals
- **Progress Analytics:** Weekly and monthly statistics
- **Feedback System:** Rate recommendations and submit detailed feedback
- **Admin Dashboard:** User management, analytics, system monitoring
- **Responsive Design:** Works on desktop, tablet, and mobile devices
- **Real-time Updates:** Firebase-powered instant data synchronization

## 🏗️ System Architecture

### Layered Architecture Diagram

```
┌─────────────────────────────────────────────────────────────────┐
│                      CLIENT LAYER                               │
│  Web Browser (HTML/CSS/JS) - Login, Dashboard, Tracker, Admin   │
└─────────────────────────────────────────────────────────────────┘
                              ↓ HTTP/HTTPS
┌─────────────────────────────────────────────────────────────────┐
│                   APPLICATION LAYER                             │
│  Flask Web Server (app.py)                                      │
│  ├── Auth Routes (/login, /signup, /logout)                     │
│  ├── Profile Routes (/profile, /create_profile)                 │
│  ├── Recommendation Routes (/get_recommendations)               │
│  ├── Tracking Routes (/tracker/*)                               │
│  └── Admin Routes (/admin/*)                                    │
└─────────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────────┐
│                  BUSINESS LOGIC LAYER                           │
│  HealthFitnessXAISystem (main.py)                               │
│  ├── DietRecommendationEngine (diet_engine.py)                  │
│  ├── ExerciseRecommendationEngine (exercise_engine.py)          │
│  ├── XAI Components (Feature Importance, Decision Factors)      │
│  └── External AI Services (Gemini API, SHAP)                    │
└─────────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────────┐
│                       DATA LAYER                                │
│  ├── Firebase Services (firebase_service.py)                    │
│  └── Daily Tracking (tracker.py)                                │
└─────────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────────┐
│                  EXTERNAL SERVICES                              │
│  ├── Firebase Cloud (Auth, Realtime DB, Storage)                │
│  ├── Google Gemini API (AI Recommendations)                     │
│  └── Google Cloud Services                                      │
└─────────────────────────────────────────────────────────────────┘
```

### Project Structure

```
health_fitness_xai/
├── Core Application
│   ├── app.py                    # Flask web server
│   ├── main.py                   # System integration
│   ├── tracker.py                # Activity tracking
│   └── llm_service.py            # Gemini API integration
│
├── Firebase Integration
│   ├── firebase_service.py       # Firebase operations
│   ├── firebase_db.py            # Firestore operations
│   ├── firebase_web_config.py    # Web configuration
│   └── firebase_credentials.json # Service account (gitignored)
│
├── AI & ML Components
│   ├── models/user_profile.py    # User data model
│   ├── engines/diet_engine.py    # Diet recommendations
│   ├── engines/exercise_engine.py# Exercise recommendations
│   └── ml_shap_explainer.py      # Advanced XAI techniques
│
├── Frontend
│   ├── templates/                # HTML templates
│   │   ├── index.html, login.html, signup.html
│   │   ├── profile.html, dashboard.html
│   │   ├── tracker.html, admin.html
│   │   └── admin_user_detail.html
│   └── static/                   # CSS, JS, assets
│
├── Configuration
│   ├── .env                      # Environment variables (gitignored)
│   ├── .gitignore
│   ├── requirements.txt
│   └── firebase_credentials.json (gitignored)
│
└── Documentation
    ├── README.md
    ├── PROJECT_SUMMARY.md        # Comprehensive diagrams & architecture
    ├── QUICK_START_GUIDE.md
    └── SECURITY_GUIDE.md
```

## 👥 Use Case Diagram

```
                        ┌──────────────┐
                        │  User System │
                        └──────────────┘
                              │
                ┌─────────────┼─────────────┐
                │             │             │
                ▼             ▼             ▼
        ┌──────────────┐ ┌──────────┐ ┌──────────┐
        │Regular User  │ │Admin User│ │Guest User│
        └──────────────┘ └──────────┘ └──────────┘
                │             │             │
    ┌───────────┼─────────┐   │             │
    │           │         │   │             │
    ▼           ▼         ▼   ▼             ▼
┌────────┐ ┌────────┐ ┌──────────┐ ┌──────────┐ ┌─────────┐
│Register│ │ Login  │ │Dashboard │ │Manage    │ │Browse   │
│Account │ │Account │ │& Profile │ │Users     │ │Info     │
└────────┘ └────────┘ └──────────┘ └──────────┘ └─────────┘
    │           │           │           │
    └───────────┼───────────┘           │
                ▼                       │
        ┌──────────────┐                │
        │Authenticated │                │
        │  Session     │                │
        └──────────────┘                │
                │                       │
    ┌───────────┼───────────┬───────────┘
    │           │           │
    ▼           ▼           ▼
┌──────────┐ ┌──────────┐ ┌──────────────┐
│Create    │ │View      │ │View Feedback │
│Profile   │ │Profile   │ │Statistics    │
└──────────┘ └──────────┘ └──────────────┘
    │           │
    ▼           ▼
┌────────────────────────────┐
│Get Recommendations         │
│(Diet & Exercise)           │
└────────────────────────────┘
    │
    ├─────────────┬──────────────┐
    ▼             ▼              ▼
┌──────────┐ ┌──────────┐ ┌──────────────┐
│View XAI  │ │Submit    │ │Track Daily   │
│Explain   │ │Feedback  │ │Activity      │
└──────────┘ └──────────┘ └──────────────┘
```

## 📊 Methodology Diagram (Compact for PowerPoint)

```
HEALTH & FITNESS XAI - METHODOLOGY FLOW

    USER INPUT
       │
    ┌──┴──┐
    │     │
  SIGNUP LOGIN
    │     │
    └──┬──┘
       │
   FIREBASE AUTH
       │
    ┌──┴──┐
    │     │
 PROFILE DASH
    │
    ▼
HEALTH METRICS
(BMI, BMR, TDEE)
    │
 ┌──┴──┐
 │     │
DIET  EXERCISE
ENGINE ENGINE
 │     │
 └──┬──┘
    │
    ▼
GEMINI API
(AI Personalization)
    │
    ▼
SHAP ANALYSIS
(Advanced XAI)
    │
    ▼
XAI EXPLANATIONS
(Feature Importance,
 Decision Factors,
 Confidence Scores)
    │
    ▼
FIREBASE DB
    │
    ▼
DASHBOARD
(4 Tabs)
    │
 ┌──┴──┐
 │     │
TRACK FEEDBACK
    │     │
    └──┬──┘
       │
    CLOUD SYNC
```

### Compact Methodology Summary
1. **User Authentication** → Firebase login/signup
2. **Profile Creation** → Collect health data
3. **Metrics Calculation** → BMI, BMR, TDEE
4. **Recommendation Engines** → Diet & Exercise planning
5. **XAI Module** → Generate explanations
6. **Database Storage** → Firebase Realtime DB
7. **Dashboard Display** → 4-tab interface
8. **Tracking & Feedback** → Daily monitoring
9. **Cloud Sync** → Real-time updates

### Presentation Prompt for Methodology Diagram

**Slide Title:** "How We Built the Health & Fitness XAI System"

**Speaker Notes:**

"Our development methodology follows a structured 9-step approach:

**Step 1-2: User Entry & Authentication**
Users begin by signing up or logging in through our Firebase authentication system. This ensures secure access and user data protection.

**Step 3: Profile Creation**
New users create a comprehensive health profile with personal information, fitness goals, and dietary preferences. Existing users proceed directly to their dashboard.

**Step 4: Health Metrics Calculation**
The system calculates three critical health metrics:
- BMI (Body Mass Index) for body composition assessment
- BMR (Basal Metabolic Rate) using the Mifflin-St Jeor formula
- TDEE (Total Daily Energy Expenditure) based on activity level

**Step 5: Recommendation Engines**
Two parallel engines process the data:
- Diet Engine: Calculates calorie targets and macronutrient distribution
- Exercise Engine: Creates personalized workout plans

**Step 5.5: Gemini API Integration**
Google Gemini API personalizes the recommendations with natural language processing, adding contextual advice and motivational guidance tailored to each user.

**Step 6: SHAP Analysis**
We use SHAP (SHapley Additive exPlanations) for advanced machine learning interpretability. This provides mathematically rigorous explanations of how each feature contributes to the final recommendation.

**Step 7: XAI Explanations**
This is our core innovation. The system generates clear explanations showing:
- Feature importance: Which factors influenced the recommendation most (powered by SHAP)
- Decision factors: Why specific choices were made
- Confidence scores: How reliable each recommendation is

**Step 7: Database Storage**
All data is securely stored in Firebase Realtime Database for cloud-based access and reliability.

**Step 8: Dashboard Display**
Users see their personalized plan across 4 intuitive tabs:
- Overview: Key metrics and goals
- Diet Plan: Calories, macros, and meal suggestions
- Exercise Plan: Weekly workout schedule
- Why This Works: Detailed XAI explanations

**Step 9: Continuous Tracking & Feedback**
Users track daily activities (steps, water, sleep, meals) and provide feedback, which helps improve future recommendations through cloud synchronization.

**Key Innovation:** The XAI module ensures users understand not just WHAT to do, but WHY—building trust and engagement through transparency."

## ��️ Entity-Relationship (ER) Diagram

```
┌─────────────────────────────┐
│         Users               │
├─────────────────────────────┤
│ PK: user_id                 │
│ email (FK)                  │
│ name                        │
│ created_at                  │
│ uid (Firebase)              │
└─────────────────────────────┘
           │ 1:1
           ▼
┌─────────────────────────────┐
│      UserProfile            │
├─────────────────────────────┤
│ PK: user_id                 │
│ age, weight, height         │
│ gender, activity_level      │
│ fitness_goal                │
│ dietary_restrictions        │
│ bmi, bmr, tdee              │
│ created_at, updated_at      │
└─────────────────────────────┘
           │ 1:N
           ├─────────────────────────────┬──────────────────────┐
           ▼                             ▼                      ▼
┌──────────────────────┐    ┌──────────────────────┐  ┌──────────────────┐
│  Recommendations     │    │    Feedback          │  │  DailyTracking   │
├──────────────────────┤    ├──────────────────────┤  ├──────────────────┤
│ PK: rec_id           │    │ PK: feedback_id      │  │ PK: tracking_id  │
│ FK: user_id          │    │ FK: user_id          │  │ FK: user_id      │
│ type (diet/exercise) │    │ feedback_type        │  │ date             │
│ content (JSON)       │    │ advice_text          │  │ steps            │
│ xai_explanation      │    │ detailed_comment     │  │ water_ml         │
│ confidence_score     │    │ timestamp            │  │ sleep_hours      │
│ created_at           │    │                      │  │ meals_completed  │
└──────────────────────┘    └──────────────────────┘  │ created_at       │
                                                      └──────────────────┘

Relationships:
- Users (1) ──→ (1) UserProfile
- UserProfile (1) ──→ (N) Recommendations
- UserProfile (1) ──→ (N) Feedback
- UserProfile (1) ──→ (N) DailyTracking
```

## � System Requirements

### Hardware Requirements
- **Processor:** Intel Core i5 or equivalent (2.0 GHz or higher)
- **RAM:** Minimum 4 GB (8 GB recommended)
- **Storage:** 500 MB free disk space for application and dependencies
- **Internet:** Stable internet connection for Firebase and Gemini API

### Software Requirements

#### Operating System
- Windows 10/11
- macOS 10.14+
- Linux (Ubuntu 18.04+, Debian 10+, CentOS 7+)

#### Programming & Runtime
- **Python:** 3.8 or higher (3.10+ recommended)
- **pip:** Package manager (comes with Python)
- **Git:** For version control (optional but recommended)

#### Required Libraries & Frameworks
- **Flask:** 2.0+ (Web framework)
- **Firebase Admin SDK:** For cloud database and authentication
- **Google Generative AI:** For Gemini API integration
- **SHAP:** For explainable AI analysis
- **NumPy & Pandas:** For data processing
- **Requests:** For HTTP requests
- **Python-dotenv:** For environment variable management

#### External Services (Cloud-based)
- **Firebase Project:** 
  - Firebase Authentication enabled
  - Firebase Realtime Database enabled
  - Service account with appropriate permissions
  
- **Google Cloud Project:**
  - Gemini API enabled
  - API key generated and configured

#### Browser Requirements
- **Minimum:** Chrome 90+, Firefox 88+, Safari 14+, Edge 90+
- **Recommended:** Latest version of Chrome or Firefox
- **JavaScript:** Must be enabled
- **Cookies:** Must be enabled for session management

### Network Requirements
- **Outbound HTTPS:** Required for Firebase and Gemini API
- **Port 5000:** Default Flask development server port (can be configured)
- **Bandwidth:** Minimum 1 Mbps for smooth operation

### Development Tools (Optional)
- **IDE:** VS Code, PyCharm, or any Python-compatible editor
- **Version Control:** Git and GitHub/GitLab account
- **API Testing:** Postman or similar tool for API testing
- **Database Viewer:** Firebase Console for database inspection

## �🚀 Installation & Setup

### Prerequisites
- Python 3.8+
- Firebase project account
- Google Gemini API key
- Git

### Step 1: Clone and Setup

```bash
# Clone the repository
git clone <repository-url>
cd health_fitness_xai

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### Step 2: Firebase Configuration

1. **Get Firebase Credentials:**
   - Go to [Firebase Console](https://console.firebase.google.com/)
   - Create a new project or select existing
   - Go to Project Settings → Service Accounts
   - Generate and download private key (JSON)
   - Save as `firebase_credentials.json` in project root

2. **Configure Realtime Database Rules:**
   - Go to Realtime Database → Rules tab
   - Replace with these permissive rules (for development):
   ```json
   {
     "rules": {
       ".read": true,
       ".write": true
     }
   }
   ```
   - Click Publish to apply rules

3. **Create `.env` file** in project root:
```env
# Firebase Configuration
FIREBASE_DATABASE_URL=https://your-project-id-default-rtdb.asia-southeast1.firebasedatabase.app
FIREBASE_API_KEY=your-firebase-api-key
FIREBASE_AUTH_DOMAIN=your-project.firebaseapp.com
FIREBASE_DATABASE_URL_WEB=https://your-project-id-default-rtdb.asia-southeast1.firebasedatabase.app
FIREBASE_PROJECT_ID=your-project-id
FIREBASE_STORAGE_BUCKET=your-project.firebasestorage.app
FIREBASE_MESSAGING_SENDER_ID=your-sender-id
FIREBASE_APP_ID=your-app-id
FIREBASE_MEASUREMENT_ID=your-measurement-id

# Google Gemini API
GOOGLE_API_KEY=your-gemini-api-key

# Flask Configuration
SECRET_KEY=your-secret-key-here
```

### Step 3: Run the Application

**Option A: Web Interface (Recommended)**
```bash
python app.py
```
Then open your browser to: http://localhost:5000

**Option B: Command-line Interface**
```bash
python main.py
```

### Step 4: Verify Setup

Run the verification script:
```bash
python verify_firebase_setup.py
```

Expected output:
```
✓ Firebase initialized successfully
✓ Firebase initialized - using cloud storage
```

## Usage

### Web Interface
1. Open the application in your browser
2. Fill in your personal information:
   - Name, age, gender
   - Weight and height
   - Activity level
   - Fitness goals
   - Dietary restrictions (optional)
3. Click "Generate My Personalized Plan"
4. View your personalized recommendations across 4 tabs:
   - **Overview:** Key metrics and expected outcomes
   - **Diet Plan:** Calorie targets, macros, and meal plans
   - **Exercise Plan:** Weekly workout schedule
   - **Why This Works:** XAI explanations and decision factors

### Command-line Interface
The `main.py` file contains a demonstration that:
- Creates a sample user profile
- Generates complete recommendations
- Displays detailed explanations
- Shows all XAI components

## 🔥 Firebase Realtime Database Structure

The application automatically syncs all user data to Firebase Realtime Database in real-time:

```
firebase-database/
└── users/
    └── {email_encoded}/
        ├── profile/
        │   ├── age: 25
        │   ├── gender: "female"
        │   ├── height: 153
        │   ├── weight: 56
        │   ├── fitness_goal: ["weight_loss"]
        │   ├── activity_level: "sedentary"
        │   ├── dietary_restrictions: ["vegan"]
        │   ├── bmi: 23.92
        │   ├── bmr: 1230.25
        │   ├── tdee: 1476.3
        │   ├── created_at: "2025-11-28T20:47:54.686383"
        │   └── updated_at: "2025-11-28T20:47:54.686383"
        │
        ├── tracking/
        │   ├── {auto_id_1}/
        │   │   ├── steps: 8500
        │   │   ├── date: "2025-11-28"
        │   │   ├── type: "steps_update"
        │   │   └── timestamp: "2025-11-28T20:50:00.000000"
        │   ├── {auto_id_2}/
        │   │   ├── water: 2000
        │   │   ├── date: "2025-11-28"
        │   │   ├── type: "water_intake"
        │   │   └── timestamp: "2025-11-28T20:51:00.000000"
        │   └── {auto_id_3}/
        │       ├── sleep: 7.5
        │       ├── date: "2025-11-28"
        │       ├── type: "sleep_update"
        │       └── timestamp: "2025-11-28T20:52:00.000000"
        │
        └── feedback/
            ├── {auto_id_1}/
            │   ├── feedback_type: "helpful"
            │   ├── advice_text: "Increase protein intake..."
            │   ├── user_email: "user@example.com"
            │   └── timestamp: "2025-11-28T20:53:00.000000"
            └── {auto_id_2}/
                ├── feedback_type: "neutral"
                ├── advice_text: "Reduce carbs..."
                ├── user_email: "user@example.com"
                └── timestamp: "2025-11-28T20:54:00.000000"
```

### Data Sync Details

**Profile Data:**
- Automatically saved when user creates or updates profile
- Synced on every page load to ensure latest data
- Contains all health metrics and personal information

**Tracker Data:**
- Saved in real-time when user logs:
  - Steps (via `/tracker/steps`)
  - Water intake (via `/tracker/water`)
  - Sleep hours (via `/tracker/sleep`)
  - Meals (via `/tracker/meal/<type>/<action>`)
  - Exercises (via `/tracker/exercise/<day>/<name>/<action>`)

**Feedback Data:**
- Saved when user clicks feedback buttons (👍 Yes, 👎 No, 😐 Neutral)
- Includes feedback type, advice text, and timestamp
- Stored with auto-generated IDs for easy retrieval

### REST API Integration

The system uses Firebase REST API with API key authentication for reliable data writes:
- Endpoint: `{FIREBASE_DATABASE_URL}/users/{email_encoded}/{data_type}.json?key={FIREBASE_API_KEY}`
- Method: PUT (for profile), POST (for tracking and feedback)
- Automatic fallback to Admin SDK if REST API fails

## XAI Components

### 1. Feature Importance
Shows the relative contribution of each user characteristic:
- Fitness goal (40%)
- Activity level (25%)
- BMI (15%)
- Age (10%)
- Current fitness (10%)

### 2. Decision Factors
Explains key factors influencing recommendations:
- **BMI Category:** Impact on calorie recommendations
- **Activity Level:** Effect on TDEE and workout frequency
- **Fitness Goal:** Determines calorie surplus/deficit and exercise split
- **Age:** Influences recovery time and exercise intensity

### 3. Transparent Calculations
All calculations are explained:
- BMR using Mifflin-St Jeor: `10 × weight + 6.25 × height - 5 × age + s`
- TDEE: `BMR × Activity Multiplier`
- Calorie deficit/surplus based on goal
- Macronutrient distribution rationale

### 4. Outcome Predictions
Predicts expected results with:
- Timeframe (4 weeks)
- Expected weight change
- Confidence level
- Scientific explanation

## Key Algorithms

### Diet Recommendation Engine
- **Calorie Calculation:** Based on TDEE with goal-specific adjustments
- **Macro Distribution:** Optimized ratios for each goal type
- **Meal Planning:** Balanced meals from nutrient database
- **Explanation Generation:** Step-by-step reasoning for each recommendation

### Exercise Recommendation Engine
- **Exercise Split:** Goal-based distribution of workout types
- **Progressive Planning:** Gradual intensity increase
- **Calorie Burn Estimation:** Weight-adjusted calculations
- **Recovery Optimization:** Built-in rest days and active recovery

## Scientific Basis

### BMR Calculation (Mifflin-St Jeor Equation)
- **Men:** BMR = 10W + 6.25H - 5A + 5
- **Women:** BMR = 10W + 6.25H - 5A - 161
- W = weight (kg), H = height (cm), A = age (years)

### TDEE Multipliers
- Sedentary: 1.2
- Lightly Active: 1.375
- Moderately Active: 1.55
- Very Active: 1.725
- Extra Active: 1.9

### Calorie-Weight Relationship
- 7700 calories ≈ 1 kg of body fat
- Safe weight loss: 0.5-1 kg/week (500-1000 cal deficit)
- Safe muscle gain: 0.25-0.5 kg/week (300-500 cal surplus)

## Advantages of This System

### 1. Trust Through Transparency
- Users understand WHY recommendations are made
- Scientific basis clearly explained
- No "black box" AI decisions

### 2. Personalization
- Every plan is unique to the individual
- Considers multiple factors simultaneously
- Adapts to different goals and restrictions

### 3. Education
- Users learn about nutrition and fitness
- Empowers informed decision-making
- Promotes long-term lifestyle changes

### 4. Safety
- Recommendations within safe limits
- No extreme diets or workout plans
- Considers age and current fitness level

## Future Enhancements

- Integration with fitness trackers (Apple Health, Google Fit)
- Machine learning for plan optimization based on user feedback
- Progress tracking and automated plan adjustments
- Social features and community support
- Mobile application (iOS/Android)
- Advanced XAI techniques (LIME, additional explainability methods)
- Meal prep and shopping list generation
- Wearable device integration
- Nutrition database expansion

## 📊 API Endpoints

### Authentication
| Method | Endpoint | Purpose |
|--------|----------|---------|
| POST | `/signup` | Register new user with Firebase |
| POST | `/login` | User login with Firebase |
| GET | `/logout` | User logout and session clear |

### Profile Management
| Method | Endpoint | Purpose |
|--------|----------|---------|
| GET | `/profile` | View user profile page |
| POST | `/create_profile` | Create health profile (syncs to Firebase) |
| POST | `/update_profile` | Update profile (syncs to Firebase) |
| GET | `/get_user_info` | Get user info as JSON |
| GET | `/api/load-profile-data` | Load profile data (syncs to Firebase) |

### Recommendations
| Method | Endpoint | Purpose |
|--------|----------|---------|
| GET | `/` | Home/Recommendations page with AI advice |
| GET | `/get_recommendations` | Get personalized diet & exercise plan |
| GET | `/export_plan` | Export plan as JSON |

### Daily Tracking
| Method | Endpoint | Purpose |
|--------|----------|---------|
| GET | `/tracker` | Daily tracker page |
| GET | `/tracker/today` | Get today's tracking data |
| POST | `/tracker/steps` | Update step count (syncs to Firebase) |
| POST | `/tracker/water` | Add water intake (syncs to Firebase) |
| POST | `/tracker/sleep` | Update sleep hours (syncs to Firebase) |
| POST | `/tracker/meal/<type>/<action>` | Mark meal status (syncs to Firebase) |
| POST | `/tracker/exercise/<day>/<name>/<action>` | Mark exercise status (syncs to Firebase) |
| POST | `/tracker/replace_food` | Replace food item in meal plan |
| GET | `/tracker/weekly` | Get weekly summary |

### Feedback System
| Method | Endpoint | Purpose |
|--------|----------|---------|
| POST | `/submit-feedback` | Submit feedback on AI advice (syncs to Firebase) |

### Admin Dashboard
| Method | Endpoint | Purpose |
|--------|----------|---------|
| GET | `/dashboard` | Admin dashboard |
| GET | `/admin` | Admin user management |
| GET | `/admin/user/<email>` | View user details |
| POST | `/admin/delete-user` | Delete user account |

### Configuration & Data
| Method | Endpoint | Purpose |
|--------|----------|---------|
| GET | `/api/firebase-config` | Get Firebase web configuration |
| POST | `/api/save-profile` | Save profile to Firebase |

## 🛠️ Technology Stack

| Component | Technology |
|-----------|-----------|
| **Backend Framework** | Flask (Python) |
| **Frontend** | HTML5, CSS3, JavaScript |
| **Database** | Firebase Realtime Database |
| **Authentication** | Firebase Auth |
| **Cloud Platform** | Google Firebase |
| **AI/ML Services** | Google Gemini API, SHAP |
| **Data Processing** | Python dataclasses, JSON |
| **Security** | HTTPS/TLS, Password Hashing (SHA-256) |
| **Deployment** | Local/Cloud ready |

## 📈 Performance Metrics

- **Page Load Time:** ~500ms
- **Recommendation Generation:** ~2-3 seconds
- **Database Operations:** ~200-500ms
- **API Response Time:** <1 second
- **Real-time Sync:** Instant (Firebase)

## Technical Details

**Backend:** Python with Flask  
**Frontend:** HTML, CSS, JavaScript  
**Data Models:** Object-oriented design with dataclasses  
**XAI Approach:** Feature importance + Decision factors + Transparent calculations  
**Cloud Integration:** Firebase (Authentication, Realtime Database, Storage)  
**AI Enhancement:** Google Gemini API for personalized advice

## 🔧 Troubleshooting

### Firebase Connection Issues

**Problem:** "Unauthorized request" when saving data to Firebase

**Solution:**
1. Ensure Firebase Realtime Database rules are set to allow writes:
   ```json
   {
     "rules": {
       ".read": true,
       ".write": true
     }
   }
   ```
2. Verify `FIREBASE_API_KEY` is set in `.env` file
3. Check that `FIREBASE_DATABASE_URL` is correct (should end with `.firebasedatabase.app`)
4. Restart the Flask server: `python app.py`

**Problem:** Profile not syncing to Firebase

**Solution:**
1. Check server logs for Firebase sync messages
2. Verify user is logged in (check session)
3. Ensure profile data is valid before saving
4. Check Firebase console to see if data exists
5. Try refreshing the page to trigger sync

**Problem:** "Firebase initialized - using local storage" message

**Solution:**
1. Verify `firebase_credentials.json` exists in project root
2. Ensure `FIREBASE_DATABASE_URL` is set in `.env`
3. Check that Firebase service account has proper permissions
4. Restart the server to re-initialize Firebase

### Data Not Appearing in Firebase Console

**Checklist:**
- ✅ User is logged in
- ✅ Profile/tracker data has been created/updated
- ✅ Firebase Realtime Database rules allow writes
- ✅ Check correct Firebase project in console
- ✅ Look under `users/{email_encoded}/` path
- ✅ Email encoding: `@` → `_`, `.` → `-`

### Performance Issues

**Slow Data Sync:**
1. Check internet connection
2. Verify Firebase project is in same region as user
3. Check for large data payloads
4. Monitor Firebase console for quota issues

## Example Output

### Sample User Profile
- Age: 30, Male, 85kg, 175cm
- Activity: Moderately Active
- Goal: Weight Loss

### Generated Recommendations
- **Daily Calories:** 2,113 (500 cal deficit from TDEE)
- **Macros:** 158g protein, 211g carbs, 70g fats
- **Weekly Exercise:** 260 min, 1,520 calories burned
- **Expected Loss:** 0.8 kg/week (3.2 kg in 4 weeks)

### XAI Explanations
- "Your BMR is 1,826 calories - this is what your body burns at rest."
- "With your moderately active lifestyle, your TDEE is 2,613 calories."
- "To lose weight safely, we've created a 500 calorie deficit."
- "High cardio proportion (60%) maximizes fat burning."

## License
This project is for educational and demonstration purposes.

## Support
For questions or issues, please refer to the code documentation or create an issue.
