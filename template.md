# Project Specification: "The Pitch" – Football Group Manager

## 1. Overview
A dedicated mobile and web application for a private football group (25–35 players). The app manages weekly statistics, team organization, and features a dynamic "FC24-style" card system with automated prestige skins.

---

## 2. User Roles & Profiles

### 2.1 Standard User Profile (FIFA Style)
* **Visual:** FC24 Ultimate Team card layout (Custom React Native Components).
* **Stats:** Matches Played (MP), Goals, Wins (Cups), and Top Scorer titles.
* **Form Guide:** A visual row of icons showing the last 5 match outcomes (e.g., `W-W-L-W-D`).

### 2.2 Dynamic Weekly Skins (Prestige System)
* **Golden Boot Skin:** Awarded to the session's Top Scorer. Features a premium "Gold" theme with animated particle effects.
* **Match Winner Skin:** Awarded to the winning team. Features a "Champion" theme (e.g., Silver/Platinum or Electric Blue).

---

## 3. Core Features

### 3.1 Home Screen: Dynamic Match Day
* **Standard State:** Displays the current "Hall of Fame" (last week's winners).
* **Match Day State:** on match day, Shows 3 teams (7 players each) and a live countdown to kickoff.

### 3.2 Team Organizer
* Logic for 3 teams. Supports both registered users and "Guest" placeholders.
* Automatic "Match Played" incrementing when a player is assigned to a team.

### 3.3 Selection Randomizer
* A utility to shuffle and rank a list of names/players 1 through $n$.

---

## 4. Visual Design System
* **Theme:** Professional Dark Mode.
* **Palette:** **[CLI TO CHOOSE]** – Create a high-contrast, premium sports palette (Avoid Neon Green). 
* **Animations:** Use `react-native-reanimated` for card transitions and the "Golden Boot" glow.

---

## 5. Technical Data Logic

### 5.1 Database Schema (Supabase/PostgreSQL)
* **Users Table:** `id, name, age, position, total_goals, total_wins, total_matches`.
* **Matches Table:** `id, date, winning_team_id`.
* **Match_Entries Table:** `id, match_id, user_id, team_id, goals_scored`.

### 5.2 Business Logic
* **Automated Stats:** Use PostgreSQL Triggers to update lifetime stats when a match entry is saved.
* **Skin Logic:** A view or function that determines `current_week_skin` based on the most recent match record.

---

## 6. Technical Stack
* **Frontend:** React Native + Expo (Web-enabled).
* **Styling:** NativeWind (Tailwind CSS) for consistent design tokens.
* **Backend:** Supabase (Auth, DB, and Realtime for the countdown).
* **Deployment:** Expo EAS (Mobile) and Vercel (Web).

---
