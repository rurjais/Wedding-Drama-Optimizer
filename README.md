# 💑 Wedding Drama Optimizer 💑

Welcome to the **Wedding Drama Optimizer 👰🤵** repository.  
Your task is to **optimize seating arrangements** for a wedding using **metaheuristics**.  

## 🔔🖨 Project Overview
In this challenge, you must arrange guests into tables while **maximizing the Overall Mood** based on the given data. The dataset includes:  
1. **Affinity scores** between guests (who likes/dislikes whom). Range: int([-5,5])
2. **Couples & Families** (who must sit together or can be separated).
3. **Social Network Relations** (which social circle the guests belong to, relative to the groom's side).

### 📂 Data Folder Structure
In the `data` folder, you will find:

- **data/**
    - `guests_120.csv` → Affinity scores for 120 guests
    - `couples.csv` → Seating constraints
    - `families.csv` → Seating constraints with kids
    - `social_network_120.csv` → Social networks between guests (120 guests)

## 🔑 TASKS

Your task is to maximize the Room Affinity Score (RAS) while also:

1. **Reducing the mean intratable affinity variance (MITAV)**
    - Reduce large affinity score differences within a table.
    - Encourage balance between high and low-affinity guests.

2. **Encouraging social group clusters in tables (SGC)**

3. These three scores contribute to the **Overall Mood** score:
        
        **Overall Mood Score** = 0.6 × (RAS) + 0.3 × (1/MITAV) + 0.1 × (SGC)

## 📌 REMARKS
- Affinity scores between guests, denoted as `Ai,j`, represent the degree of liking or disliking between guest `i` and guest `j`. The scores generally lie within the range `Ai,j ∈ [−5, 5]`, with the **Despicable score** being an exceptional value of `Ai,j = −15`, which represents strong dislike and is valid within the model's context.
- The Affinity scores `Ai,j` and `Aj,i` may not be identical (good or bad relationships are not always reciprocal), but the **Despicable score** is.
- Please be aware that restrictions over **Couples** & **Families** separation must be enforced: Couples **cannot** be separated; Families that are allowed to be separated are properly highlighted.
- The arrangement of your guests must also fit within these table size constraints:
    - 7 seats: 9 tables (max)
    - 8 seats: 9 tables (max)
    - 9 seats: 8 tables (max)

Any combination of this set of tables is allowed. No empty seats are permitted.