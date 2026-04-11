# nextstep
## Mentor Matching System
### Student–Mentor Matching Algorithm
This project implements a weighted scoring system that takes a student’s profile as input and returns a ranked list of suitable mentors, along with a breakdown of scores. It is based on the student–mentor schema designed earlier and tries to make the matching process more structured and explainable.

### How the Algorithm Works
The algorithm evaluates each mentor using six different signals, assigns weights to each of them, and calculates a final score out of 100.

### Pipeline:
student input → scoring functions → weighted sum → ranked mentor list

Each mentor also gets a per-signal breakdown, so the result is easy to interpret instead of being a black-box score.s.

---

### Scoring Logic 
* Stage Alignment:
Exact year match is required. Extra score if the mentor’s decisions match the student’s focus.
* Confusion Type:
Uses a compatibility matrix instead of exact matching, since similar confusion types can still help.
* Domain Overlap:
Takes the best matching domain instead of averaging, since one strong match is more useful.
* Advising Confidence:
Looks at relevant topics first, then checks confidence level (high/medium/low).
* Mentoring Style:
Uses a predefined table based on personality + guidance preference.
* Recency:
Step-based scoring depending on years since graduation.
Dataset Overview
Around 20 mentor profiles
Covers multiple branches (CSE, EE, Mechanical, Aerospace, etc.)
* Includes variety of outcomes: core jobs, non-core roles, research, higher studies, startups

This diversity helps test the algorithm across different career paths.

This approach was chosen because:

- It is **interpretable** — the system can explain why a mentor was recommended  
- It works well with **small datasets** (20 mentors)  
- The schema already defines meaningful features, so rules can directly encode them  

The system also returns a **detailed breakdown** of scores, making the recommendations transparent.

---

## Scoring Design

The weights used are:

| Signal | Weight |
|--------|--------|
| Stage Alignment | 25 |
| Confusion Type | 20 |
| Domain Overlap | 20 |
| Advising Confidence | 15 |
| Mentoring Style | 12 |
| Recency | 8 |

Total = 100

The design prioritizes **relevance first** (stage, confusion, domain), followed by **quality of interaction** (confidence, style, recency).

---

## Key Design Decisions

- **Rule-based over ML**: Chosen due to limited data and need for explainability  
- **Compatibility matrices**: Used for confusion type and mentoring style instead of exact matching  
- **Weighted scoring**: Allows flexible tuning of importance of different signals  
- **Breakdown output**: Each score is accompanied by a rationale for transparency  

---

## Known Limitations

1. **Domain exploration depth is simplified**  
   All domains are treated as “Attempted”, even though deeper levels like “Worked” or “Researched” exist.  
   → This reduces accuracy in domain scoring.

2. **Confusion compatibility is manually defined**  
   The compatibility matrix is based on assumptions rather than real data.  
   → It may not fully reflect real-world mentor effectiveness.

3. **Stage alignment is weak as a standalone signal**  
   All mentors have gone through all years, so year matching alone is not very discriminative.  
   → It relies heavily on decision similarity.

4. **No mentor availability or capacity handling**  
   The system does not account for how many students a mentor can handle.

5. **Domain matching is string-based**  
   It only matches exact terms (e.g., “AI” ≠ “Artificial Intelligence”).

6. **Branch is not currently used**  
   Although available, branch is not included in scoring. It could improve results for academic or core-specific queries.

---

## Future Improvements

- Learn weights dynamically from user feedback  
- Replace string matching with semantic similarity (embeddings)  
- Improve domain modeling with per-domain exploration levels  
- Learn confusion compatibility from real interaction data  
- Add mentor availability and capacity constraints  
- Introduce hybrid model (rule-based + ML)

---

## Conclusion

This system provides a **simple, interpretable, and effective baseline** for mentor matching.  
It is designed to be extensible and can evolve into a more data-driven system as more usage data becomes available.

## Assignment questions 
### Why did you choose this approach?

I chose a weighted scoring approach instead of using machine learning mainly because I wanted the system to be easy to understand and explain.   
First, explainability is important here a student should be able to see why a mentor was recommended. A weighted system makes it possible to show exactly which factors contributed to the final score, whereas a neural model would just give a number without clear reasoning.  
Second, the dataset is quite small (around 20 mentors), so using ML wouldn’t be very effective. A rule-based approach works better in this kind of structured, low-data setting.   
Finally, the schema already defines what matters (like confusion type, stage, and domain). So instead of trying to “learn” these relationships again, I directly used them in the scoring logic.

---

### What signals carry the most weight and why?

The most important signals are stage alignment, confusion type, and domain overlap, since they determine whether the mentor is actually relevant to the student.
* Stage alignment (25%)
This acts as a basic filter. Advice is most useful when it comes from someone who has faced similar decisions at the same stage. However, just having the same stage is not enough — the mentor’s decisions during that stage also matter.
* Confusion type (20%)
This is one of the most important parts of the system. Two students in the same domain and year can still need completely different types of guidance depending on how they are confused (e.g., overwhelmed vs lack of information).
* Domain overlap (20%)
This ensures the mentor has experience in the student’s area of interest. It becomes especially strong when the mentor is currently working in that domain.    
The remaining signals advising confidence, mentoring style, and recency help improve the quality of the interaction, but are slightly less important than relevance.
---

### Where does the algorithm break down?
* Exploration stage is not stored per domain
Right now, all matched domains are treated as “Attempted”, even though the schema allows more detailed levels like Worked or Researched. This flattens meaningful differences in experience.
→ Fix: store exploration stage separately for each domain.
* Confusion compatibility is manually defined
The compatibility matrix is based on assumed relationships between confusion types rather than real data.
→ Fix: learn these values from user feedback (e.g., session ratings).
* Stage alignment is somewhat weak
Since every mentor has gone through all years, just matching the year doesn’t differentiate much. The real signal comes from what decisions they made in that stage.
→ Fix: reduce base score for year match and rely more on decision similarity.
* No concept of mentor availability
The system may repeatedly match students to the same high-scoring mentor without considering their capacity.
→ Fix: introduce a capacity or availability constraint before ranking.
* Domain matching is too basic (string-based)
It only matches exact terms, so similar domains may not align (e.g., “AI” vs “Artificial Intelligence”).
→ Fix: use semantic similarity (embeddings or synonym mapping).
* Branch is not currently used
Branch is captured but not included in scoring. This was intentional, since it is only relevant in specific cases.
→ Fix: use branch as a conditional signal, applied only when the student’s problem is academic or domain-specific, so it improves precision without adding noise.
