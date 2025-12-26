# Project Specification: "The Pitch" – Football Group Manager

## 1. Overview
A dedicated mobile and web application for a private football group (25–35 players). The app manages weekly statistics, team organization, and features a dynamic "FIFA-style" card system that rewards performance with special visual skins.

---

## 2. User Roles & Profiles

### 2.1 Standard User Profile (FIFA Style)
The profile is represented by a **FIFA/FC24 Ultimate Team card**.
* **Personal Details:** First Name, Last Name, Age, and Preferred Position.
* **Core Statistics:**
    * **Matches Played:** Automatically calculated based on team assignments.
    * **Total Goals Scored.**
    * **Total Wins (Cups Won).**
    * **Top Scorer Titles.**
* **Form Guide:** A visual sequence (e.g., **W W L W D**) showing results of the last 5 games.

### 2.2 Dynamic Weekly Skins (Prestige System)
Player cards change their visual appearance based on the results of the most recent session.

#### A) "King of Goals" (Top Scorer Skin)
If a player was the Top Scorer in the latest session, their card is upgraded to the **Golden Boot Week** skin.
* **Visuals:** Animated gold glow, premium frame, and subtle particle effects.
* **Badge:** A "TOP SCORER - WEEK" ribbon displayed on the card.
* **Duration:** Active until the next session's results are submitted.
* **Tie-Breaker:** If multiple players tie for most goals, all receive the skin.

#### B) "Match Winners" (Winning Team Skin)
Every player on the winning team receives a special "Winner" design.
* **Visuals:** Team-colored accents, silver shine effect, and a winner ribbon.
* **Badge:** "WINNER - WEEK" badge.
* **Hierarchy:** If a player is both a Winner and a Top Scorer, the **Top Scorer Skin** takes visual priority (or they combine effects).

---

## 3. Core Features

### 3.1 Home Screen: Dynamic Match Day
On session days, the UI transforms into a "Match Center":
* **The 3 Teams:** Detailed rosters for the 7-a-side teams.
* **Kickoff Countdown:** Live timer counting down to game time.
* **Active Skins:** Displaying the current "Top Scorer" and "Winners" from the previous week.

### 3.2 Statistics & Leaderboard
* **Global Leaderboard:** Sortable by all core metrics.
* **Skin Visibility:** The special skins are visible everywhere (Leaderboard, Profile, and Match Center).
* **Automated Tracking:** Assigning a player to a team automatically counts as a "Match Played."

### 3.3 Selection Randomizer
* **Function:** Ranks $n$ players/names randomly to determine team selection order.

---

## 4. Visual Design System



* **Theme:** **Dark Mode** (Deep Charcoal / Navy Blue).
* **Accent Color:** **Neon Green** (Pitch Green) for standard UI.
* **Special Colors:** **Gold/Yellow** (Top Scorer) and **Electric Blue/Silver** (Winners).
* **Card UI:** Rounded corners, high-quality player avatars, and bold "FIFA-style" stat numbers.

---

## 5. Technical Requirements & Stack

* **Cross-Platform:** Flutter (Web, iOS, Android).
* **Database:** **PostgreSQL (via Supabase)**.
* **Skin Logic:** A `current_status` flag in the database that updates weekly when the Admin submits the match report.

| Component | Technology |
| :--- | :--- |
| **Frontend** | Flutter |
| **Backend** | Supabase (Postgres + Auth) |
| **Animations** | Lottie or Rive (for card glows and particles) |

---
