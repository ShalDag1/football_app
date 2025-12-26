# Project Specification: "The Pitch" – Football Group Manager

## 1. Overview
A dedicated mobile and web application designed for a private group of 25–35 friends to manage weekly football sessions. The app focuses on tracking individual performance statistics, facilitating team organization, and determining player selection order via a randomization tool.

---

## 2. User Roles & Profiles

### 2.1 Standard User Profile
Every player must register an account with a username and password.
* **Personal Details:** First Name, Last Name, Age, and Preferred Position (e.g., Forward, Midfielder, Defender, Goalkeeper).
* **Performance Metrics:** Users can view their lifetime statistics, including:
    * **Total Goals Scored**
    * **Total Wins (Cups Won)**
    * **Top Scorer Titles** (Number of weeks finished as the leading goalscorer).

### 2.2 Admin Profile
Admins possess all standard user capabilities plus the following privileges:
* **Data Entry:** Input and submit match statistics (goals, wins, top scorers) following each session.
* **User Management:** Add and manage users within the system.
* **Team Management:** Finalize weekly team rosters and designate the winning team.

---

## 3. Core Features

### 3.1 Statistics & Leaderboard
This is the primary feature of the app, used for performance tracking and team scouting.
* **Global Leaderboard:** A sortable table displaying all players. Users can sort by Goals, Wins, or Top Scorer titles.
* **Filtering:** Ability to filter statistics by specific date ranges.
* **Top Scorer Logic:** If multiple players share the highest goal count in a single week, all involved players are credited with a "Top Scorer" title for that session.

### 3.2 Team Organizer
* **Structure:** Support for 3 teams per session, with exactly 7 players per team.
* **Flexibility:** Admins or users can assign registered players to teams or use "Guest Names" for one-time players.
* **Result Submission:** After the match, the Admin selects the winning team, automatically awarding a "Cup" to those 7 players.

### 3.3 Selection Randomizer
A tool to help team leaders determine the order of player selection.
* **Input:** Choose from existing users or enter custom names.
* **Output:** Generates a randomized list ranked $1$ to $n$ to decide the selection sequence.

---

## 4. Technical Requirements

* **Cross-Platform:** The app must be accessible as a web application and as a downloadable app for both iOS and Android.
* **Database:** A relational database is preferred. **PostgreSQL** is the primary choice for data integrity and future scalability.
* **Scalability:** The architecture should be modular to allow for the addition of new features in future versions (Beta Phase).
* **Security:** High-level security is not a priority for this internal tool; simple authentication is sufficient.

---

## 5. Recommended Technology Stack

| Component | Technology Recommendation |
| :--- | :--- |
| **Frontend** | **Flutter** (Single codebase for Web, iOS, and Android) |
| **Backend/DB** | **Supabase** (Hosted PostgreSQL, Auth, and API) |
| **Hosting** | **Vercel** (for Web) and **App Store/Play Store** (for Mobile) |

---
