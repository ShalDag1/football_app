# Project Specification: "The Pitch" – Football Group Manager

## 1. Overview
A dedicated mobile and web application for a private football group (25–35 players). The app manages weekly statistics, team organization, and features a dynamic "FIFA-style" card system with automated prestige skins.

---

## 2. User Roles & Profiles

### 2.1 Standard User Profile (FIFA Style)
* **Visual:** FIFA/FC24 Ultimate Team card layout.
* **Stats:** Matches Played (MP), Goals, Wins (Cups), and Top Scorer titles.
* **Form Guide:** A calculated array of the last 5 match outcomes (e.g., `['W', 'W', 'L', 'W', 'D']`).

### 2.2 Dynamic Weekly Skins (Prestige System)
* **Golden Boot Skin:** Awarded to the player(s) with the `MAX(goals)` in the most recent session.
* **Match Winner Skin:** Awarded to all 7 players belonging to the `winning_team_id` of the most recent session.

---

## 3. Core Features

### 3.1 Dynamic Match Day Home Screen
* **State A (Standard):** Displays last week's "King of Goals" and "Winners."
* **State B (Match Day):** Triggered by Admin. Displays the 3 team rosters and a live JS-based countdown timer to kickoff.

### 3.2 Team Organizer
* 3 Teams | 7 Players per Team.
* Supports "Guest" placeholders (names not linked to a User ID).

### 3.3 Selection Randomizer
* Randomly ranks a selected list of names 1 through $n$.

---

## 4. Visual Design System
* **Theme:** Dark Mode (Background: `#121212`, Surface: `#1E1E1E`).
* **Primary Accent:** Neon Green (`#39FF14`).
* **Special Effects:** CSS/Flutter linear-gradient animations for Golden Boot cards.

---

## 5. Technical Data Logic (For AI Implementation)

### 5.1 Database Schema (Relational)


* **Users Table:** `id, name, age, position, total_goals, total_wins, total_matches`.
* **Matches Table:** `id, date, winning_team_id (nullable)`.
* **Match_Entries Table:** `id, match_id, user_id, team_id, goals_scored`.

### 5.2 Business Logic Calculations
* **Form Guide Logic:** `SELECT outcome FROM match_entries WHERE user_id = :id ORDER BY match_date DESC LIMIT 5;`
* **Top Scorer Logic:**
    1. Filter `match_entries` for the latest `match_id`.
    2. Identify `user_id` where `goals_scored` equals the maximum value in that set.
* **Matches Played (Auto):**
    Trigger: Whenever a row is created in `match_entries`, increment `users.total_matches`.

---

## 6. Technical Stack
* **Frontend:** Flutter (Web/iOS/Android).
* **Backend/Auth:** Supabase (PostgreSQL).
* **Logic Processing:** Supabase Edge Functions (TypeScript).

---
