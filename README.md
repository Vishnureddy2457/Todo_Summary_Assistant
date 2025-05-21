# 📌 Todo Summary Assistant  
A **full-stack task management app** that allows users to:  
- **Create, edit, delete** personal to-dos.
- **Summarize pending tasks** using an **LLM (Large Language Model)** like **OpenAI GPT**.
- **Send summaries to Slack** using Incoming Webhooks.
- **Store data** in Firebase Firestore.

## 🏗️ Tech Stack  
**Frontend**: React.js, TailwindCSS, Firebase  
**Backend**: Node.js (Express), Firebase Admin SDK  
**Database**: Firestore (Firebase)  
**LLM Integration**: OpenAI API  
**Slack Integration**: Incoming Webhooks  

---

## 🚀 **Getting Started**  

### 📌 **1. Clone the Repository**  
```sh
git clone https://github.com/your-username/todo-summary-assistant.git
cd todo-summary-assistant
```

### 📌 **2. Set Up Firebase**  
1. Create a Firebase project [here](https://console.firebase.google.com/).  
2. Enable **Firestore Database**.  
3. Create a **collection** called `todos`.  
4. Update **Firestore Rules** (for development only):  
   ```js
   rules_version = '2';
   service cloud.firestore {
     match /databases/{database}/documents {
       match /todos/{todoId} {
         allow read, write: if true;
       }
     }
   }
   ```
5. Enable **Firebase Authentication** (optional).  

### 📌 **3. Install Dependencies**  

#### **Frontend**
```sh
cd frontend
npm install
```

#### **Backend**
```sh
cd backend
npm install
```

---

## ⚙️ **Environment Variables (`.env`)**  

Create a `.env` file in both `frontend` and `backend` directories:

### 🔹 **Frontend (`frontend/.env`)**  
```
REACT_APP_FIREBASE_API_KEY=your-api-key
REACT_APP_FIREBASE_AUTH_DOMAIN=your-auth-domain
REACT_APP_FIREBASE_PROJECT_ID=your-project-id
REACT_APP_FIREBASE_STORAGE_BUCKET=your-storage-bucket
REACT_APP_FIREBASE_MESSAGING_SENDER_ID=your-messaging-sender-id
REACT_APP_FIREBASE_APP_ID=your-app-id
```

### 🔹 **Backend (`backend/.env`)**  
```
OPENAI_API_KEY=your-openai-api-key
SLACK_WEBHOOK_URL=your-slack-webhook-url
FIREBASE_PROJECT_ID=your-project-id
FIREBASE_PRIVATE_KEY="your-private-key"
FIREBASE_CLIENT_EMAIL=your-client-email
```

---

## 🏗️ **How to Run the Project**  

### 🔹 **Run Frontend**  
```sh
cd frontend
npm run dev
```

### 🔹 **Run Backend**  
```sh
cd backend
node server.js
```

---

## 📌 **API Endpoints**  

| Method | Endpoint            | Description |
|--------|--------------------|-------------|
| GET    | `/todos`           | Fetch all todos |
| POST   | `/todos`           | Add a new todo |
| DELETE | `/todos/:id`       | Delete a todo |
| POST   | `/summarize`       | Summarize todos & send to Slack |

---

## 🔥 **LLM & Slack Integration**  

### ✅ **LLM (OpenAI GPT)**
- Generates a meaningful summary of pending todos.
- Uses **OpenAI API** to process the task list.

### ✅ **Slack Integration**
- Sends the generated summary to a **Slack channel** using Incoming Webhooks.

---

## 🚀 **Deployment**  

### 🔹 **Frontend Deployment (Firebase Hosting)**  
```sh
firebase login
firebase init
firebase deploy
```

### 🔹 **Backend Deployment (Firebase Functions or Supabase)**  
If using Firebase Functions:  
```sh
firebase deploy --only functions
```

If using Supabase:  
```sh
supabase start
```


