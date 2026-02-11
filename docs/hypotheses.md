# Titanic — Hypotheses & Findings

> All hypotheses were written **before** looking at the data, then validated through EDA.

---

## Main Research Question

**Which factors increased or decreased a passenger's chance of survival in the Titanic disaster?**

---

## Hypothesis 1: Gender Effect

**Question:** Did women survive at a higher rate than men?

**Prediction:** Women would have a 70%+ survival rate; men around 20-30%.

**Reasoning:** The "women and children first" maritime rule was applied during the Titanic sinking. Women were given priority access to lifeboats.

**Findings:**
- Women survival rate: **~74-75%**
- Men survival rate: **~18-19%**

✅ **Confirmed.** The gender gap is stark and directly reflects the lifeboat boarding policy.

---

## Hypothesis 2: Socioeconomic Status (Passenger Class)

**Question:** Did upper-class passengers survive at a higher rate?

**Prediction:** 1st class ~60%, 2nd class ~45-50%, 3rd class ~25-30%.

**Reasoning:** First-class cabins were on upper decks, closer to lifeboats. Third-class passengers were on lower decks with restricted access.

**Findings:**
- 1st class: **~63%**
- 2nd class: **~47%**
- 3rd class: **~24%**

✅ **Confirmed.** Survival rate drops significantly with class.

---

## Hypothesis 3: Age Effect

**Question:** Did children survive more? How about the elderly?

**Prediction:** Children (0-12) ~55-60%, young adults (13-25) ~40-45%, adults (26-60) ~35-40%, elderly (60+) ~25-30%.

**Reasoning:** "Women and children first" rule gave priority to children. Elderly passengers had limited mobility.

**Findings:**
- Children: **~58%**
- Young: **~43%**
- Adults: **~38%**
- Middle-aged: **~40%**
- Elderly: **~23%**

✅ **Confirmed.** Survival rate decreases with age.

---

## Hypothesis 4: Family Ties

**Question:** Did passengers traveling with family have better odds than solo travelers?

**Prediction:** Medium families (2-4 people) best ~50%+, solo travelers ~30-35%, large families (6+) ~20-25%.

**Reasoning:** Small families could help each other and move together. Solo travelers may have panicked. Very large families lost time gathering everyone.

**Findings:**
- Family size 4: highest survival rate **~72%**
- Solo travelers (family size 1): **~30%**
- Large families (5-6): **~13-20%**

✅ **Confirmed.** Medium-sized families had a clear advantage.

---

## Hypothesis 5: Ticket Fare

**Question:** Did passengers who paid more survive at higher rates?

**Prediction:** Highest fares → 60%+ survival; lowest fares → 25-30%.

**Reasoning:** Higher fare correlates with upper decks and better class. These passengers had proximity to lifeboats and possibly preferential treatment.

**Findings:**
- Survivors had significantly higher fare values in boxplot analysis.
- Fare distribution is right-skewed; most passengers paid low fares.
- Higher fare strongly correlates with survival.

✅ **Confirmed.** Fare is closely linked to Pclass and indirectly to survival.

---

## Hypothesis 6: Embarkation Port

**Question:** Which port of embarkation had the highest survival rate?

**Prediction:** Cherbourg (C) ~50-55% (wealthy passengers), Southampton (S) and Queenstown (Q) ~35-40%.

**Reasoning:** Cherbourg is a luxury port in France — mostly upper-class passengers. Southampton had many 3rd-class passengers. Queenstown had poor Irish emigrants.

**Findings:**
- Cherbourg (C): **~55%**
- Queenstown (Q): **~39-40%**
- Southampton (S): **~33-34%**

✅ **Confirmed.** Embarkation port is a proxy for socioeconomic status.

---

## Hypothesis 7: Cabin Information

**Question:** Did passengers with a known cabin survive more?

**Prediction:** Cabin known → 55-60% survival; cabin unknown → 30-35%.

**Reasoning:** Having a cabin number indicates a private cabin reservation, typically 1st or 2nd class. Cabin letter (A-G) also indicates deck level.

**Findings:**
- Cabin known: **~67%**
- Cabin unknown: **~30%**

✅ **Confirmed.** Cabin info is a strong indicator of class and deck proximity.

---

## Hypothesis 8: Title / Social Status

**Question:** Do titles (Mr, Mrs, Miss, Master, etc.) predict survival?

**Prediction:** Mrs/Miss ~70%+, Master (boys) ~60%+, Mr ~15-20%, Rare titles ~30-40%.

**Reasoning:** Title encodes both gender and age. Mrs/Miss = female advantage. Master = child advantage. Mr = adult male, most disadvantaged.

**Findings:**
- Mrs: **~79%**
- Miss: **~70%**
- Master: **~57%**
- Rare (Dr, Rev, Col, etc.): **~45%**
- Mr: **~15-16%**

✅ **Confirmed.** Title is one of the most powerful predictors.

---

## Interaction Hypotheses

### Gender × Class
- **Prediction:** 1st/2nd class women ~90%+, 3rd class women ~45-55%, 1st class men ~30-35%, 3rd class men ~10-15%.
- **Finding:** 1st class women had near-perfect survival (~96.8%). 3rd class men had the lowest (~13.5%).

### Age × Gender
- **Prediction:** Boy children ~55-65%, girl children ~70-80%.
- **Finding:** Consistent with predictions — female children had the highest combined advantage.

---

## Summary

| Factor | Strength | Direction |
|--------|----------|-----------|
| Sex | ★★★★★ | Female → Higher survival |
| Pclass | ★★★★☆ | Higher class → Higher survival |
| Title | ★★★★☆ | Mrs/Miss/Master → Higher survival |
| Fare | ★★★★☆ | Higher fare → Higher survival |
| Age | ★★★☆☆ | Younger → Higher survival |
| CabinKnown | ★★★☆☆ | Known cabin → Higher survival |
| FamilySize | ★★★☆☆ | 2-4 family → Higher survival |
| Embarked | ★★☆☆☆ | Cherbourg → Higher survival |

**Most powerful predictors for modeling:** Sex, Pclass, Title, Fare, Age, FamilySize.
