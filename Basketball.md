# 🏀 Basketball Sport System: Logical Data Model

## 1. Introduction
This logical data model is designed to capture the **Basketball Sport System**.  
The objective is to provide a clear structure for how entities interact and to ensure consistency when storing and analyzing sports data.

<img width="1561" height="1030" alt="Logical_Data_Model_Basketball" src="https://github.com/user-attachments/assets/ede7c413-2104-41b8-ad91-2129337b2afe" />

---

## 2. Entities

### Coach
Each coach is uniquely identified and contains personal and professional information.  

### Player
Each player has a unique identifier and is linked to exactly one coach.  

### Game
Each game is uniquely identified and belongs to a specific season.  

### Season
Each season represents a defined competition period containing multiple games.  

### Player_Game (Associative Entity)
This entity resolves the many-to-many relationship between players and games while storing performance data.  

---

## 3. Business Rules

### Coach–Player
- A player must be assigned to one coach.  
- A coach may train multiple players.  
- **Cardinality:** One-to-Many (1:N).

### Player–Game
- A player can participate in many games.  
- A game includes many players.  
- **Cardinality:** Many-to-Many (M:N), resolved via `Player_Game`.

### Season–Game
- Each game belongs to exactly one season.  
- A season consists of many games.  
- **Cardinality:** One-to-Many (1:N).

---

## 4. Relationship Descriptions

- **Coach to Player:**  
  This relationship enforces accountability and ensures each player is guided by a coach. It supports performance analysis by grouping players under a coach.

- **Player to Game:**  
  This relationship captures participation and performance data at the game level, allowing player statistics to be analyzed across different matches.

- **Season to Game:**  
  This relationship provides the temporal and organizational structure for competitions. It allows aggregation of performance and results across a full season.

---

## 5. Conclusion
The logical data model captures the essential relationships in a sports context.  
By clearly defining entities, attributes, and business rules, the system supports both **operational needs** (tracking games, players, and coaches) and **analytical needs** (evaluating performance across games and seasons).
