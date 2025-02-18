# 💑 Wedding Drama Optimizer 💑

Welcome to the **Wedding Drama Optimizer 👰🤵**  repository  
Your task is to **optimize seating arrangements** for a wedding using **metaheuristics**.  

## 🔔🖨 Project Overview
In this challenge, you must arrange guests into tables while **maximizing Overall Mood** based on given data. The dataset includes:  
1. **Affinity scores** between guests (who likes/dislikes whom). Range: int([-5,5])
2. **Couples & Families** (who must sit together or you can separate apart).
3. **Social Network Relation** (to what social circle the guests belong to, relative to the grooms)  

## 📜 Dataset Description
In the `data` folder you will find:
data/ 
├── guests_120.csv # Affinity scores for 120 guests
├── couples.csv # Seating constraints
├── families.csv # Seating constraints with kids
├── social_network_120.csv # Social Networks between guests (120 guests)

## 🔑 TASKS
1. Your task is to maximize the Room Afinity Score (RAS) while also: 
    1.1. reducing the mean intratable affinity variance (MITAV)
    1.2. encouring social groups clusters in the tables (SGC)
2. These 3 scores lead you to the **Overall Mood** score:
    2.1.  The objective score = 0.6*(Room_Affinity_Score) + 0.3*(1/MITAV) + 0.1*(SGC)
 

## 📌 REMARKS
- Affinity Scores between guests, denoted as `Ai,j`, representing the degree of liking or disliking between guest `i` and guest `j`. The scores generally lie within the range `Ai,j∈[−5,5]`, along with the **Discpicable score** of exceptional values `Ai,j=−15`, which represent specific instances of strong dislike and are valid within the model's context.
- The Affinity Scores `Ai,j`, `Aj,i` might not be identycal (good or bad relationships are not reciprocal), but the **Discpicable score** is.
- Plase be aware that restrictions over **Couples** & **Families** separation must be enforced: Couples **can not** be separated; Families that are allowed to be separated are properly highlighted;
- The arrangement of your guests must be also be fitted in this tabble size constrains:
    - 7 seats: 9 tables (max)
    - 8 seats: 9 tables (max)
    - 9 seats: 8 tables (max)
Either combination of this set of tables is allowed. No empty places are allowed.