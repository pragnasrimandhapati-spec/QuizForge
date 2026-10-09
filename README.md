# QuizForge — Quiz Management System

Responsive HTML, CSS, Bootstrap and JavaScript quiz app with distinct student/admin roles, accounts, quiz authoring and scheduling, attempts, scores, upcoming-quiz updates, and Python, Java, SQL, C++ and .NET tracks.

## Run

Open `index.html` in a modern browser. For best results, serve this folder with a local static server such as `python -m http.server 8000` and visit `http://localhost:8000`.

The app starts in demo mode. Demo accounts, quizzes, attempts, and schedules use browser localStorage; the signed-in session uses sessionStorage. Register one student and one admin account to explore both roles. Demo passwords are stored locally and are not suitable for real users.

Admins can publish a quiz with custom questions. Each question occupies one line in this format:

`Question text | Option A | Option B | Option C | Option D | correct option (1–4)`

## Firebase

`firebase-config.js` documents the optional Firebase Auth setup. Add the Firebase compat app/auth scripts and config, and enable Email/Password authentication in the Firebase console. Auth is wired; quiz data uses the local demo model until connected to Firestore.

For production, implement Firestore persistence and security rules or trusted Cloud Functions to authorize admin actions, enforce one attempt per student, calculate scores, and manage exclusive sessions. Client-side restrictions are a demo safeguard only: localStorage coordination cannot enforce cross-device or tamper-proof rules. Do not store passwords in application data.
