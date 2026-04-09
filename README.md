# nextstep_assignment
3 questions 

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
