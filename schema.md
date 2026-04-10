 # **Data Schema Design for Student–Mentor Matching**

## **1. Student Schema**

The student schema is designed to capture the student’s **current stage, nature of confusion, and decision context**, with year-wise buckets reflecting how decisions evolve over time.

---

## **1.1 Common Fields (Applicable to All Students)**

- **Year**
    
    Identifies the stage of the student; ensures mentors are matched who have faced similar stage-specific decisions. 
    
- **Branch**
    
    Provides academic context; enables matching with mentors from similar backgrounds. Matters when the problem is academic and student wants to go into core or explore his departments opportunities  and students needs support 
    
- **Personality Type (Introvert / Extrovert / Ambivert)**
    
    Influences how students approach opportunities and decisions; helps align with mentors having similar behavioral tendencies and also mentor understand the student.
    
- **Problem Category (Academic / Career / Personal / Time Management / FOMO)**
    
    Categorizes the broad nature of the issue; allows routing to mentors experienced in that or similar problem type .
    
- **Confusion Type (Indecision / Lack of Information / Overwhelmed / FOMO)**
    
    Captures the root cause of confusion; distinguishes between need for clarity, information, or reassurance.
    
- **Interest Fields (list of domains)**
    
    Indicates areas the student is considering; enables matching with mentors who have explored or worked in those domains.
    
- **Interest Certainty Level (Low / Medium / High)**
    
    Differentiates between exploration and commitment ; helps match with mentors who explored broadly or committed early .
    
- **Decision Urgency (Immediate / Exploring)**
    
    Captures time pressure; ensures alignment with mentors who made decisions under similar urgency and faced this pressure.
  ## **1.2 First Year (Exploration & Adjustment Stage)**

- **Adjustment Level to Institute Life (Low / Medium / High)**
    
    Reflects ease of transition; matches with mentors who faced similar adaptation challenges.
    
- **Clubs/Extracurriculars Explored (NSS / NSO / Technical / Cultural / IB)**
    
    Indicates exposure to opportunities; aligns with mentors with similar exploration patterns.
    
- **Role Interest (Not Interested / Exploring / Targeting POR)**
    
    Shows leadership inclination; connects with mentors who pursued or avoided leadership roles.
    
- **Academic Comfort Level (Struggling / Average / Comfortable)**
    
    Captures academic adaptation; matches with mentors who handled similar academic situations.
    
- First-Year Adjustment Concern(Finding intrests / peer group / managing time etc )
    
    Specifies early-stage uncertainty; improves precision in mentor matching.
    
- **Awareness Level of Opportunities (Low / Medium / High)**
    
    Distinguishes lack of exposure from overthinking; ensures mentors address the correct gap
  ## **1.3 Second Year (Direction & Decision Stage)**

The second year is a critical stage where students transition from exploration to decision-making, especially regarding internships, skills, and career direction. To ensure efficient and relevant data capture, the schema follows a **conditional (adaptive) structure**, where deeper questions are asked only when a student indicates a specific area of concern.

---

### **Step 1: Identify Primary Focus Area**

Each student first selects their primary area of concern:

student can choose multiple fields in this 

- Internship
- Courses / Academics
- Career Direction
- Skill Development
- Exploration (not sure yet)

This field acts as a routing mechanism, ensuring that only relevant follow-up questions are asked, thereby reducing unnecessary complexity and improving matching precision.

---

### **Step 2: Base Fields (Applicable to All Students)**

- **Current Involvements (Clubs/PORs with role level)**
    
    Reflects workload and level of responsibility; enables matching with mentors who managed similar commitments.
    
- **Core vs Non-Core Inclination (Core / Non-core / Undecided)**
    
    Captures a key career branching decision; aligns students with mentors who made similar choices.
    
- **Skill Roadmap Clarity (No Idea / Some Direction / Clear Plan)**
    
    Indicates the level of planning and direction; helps match with mentors who structured or struggled with skill development.
    
- **Future Planning Stage (None / Rough Idea / Clear Plan)**
    
    Reflects long-term clarity; aligns with mentors at similar stages of career planning.
    

---

### **Step 3: Conditional Fields Based on Primary Focus**

### **A. If Primary Focus = Internship**

- **Internship Intent (Actively pursuing / Unsure / Not interested)**
    
    Differentiates between serious pursuit and uncertainty.
    
- **Internship Status (Not started / Preparing / Applied / Secured)**
    
    Captures current progress in the internship process.
    
- **Internship Concern Type (multi-select)**
    - Don’t know where to apply
    - Don’t know how to prepare
    - Not getting shortlisted
    - Resume issues
        
        Identifies specific bottlenecks, enabling targeted mentor matching.
        
- **Target Internship Domains**
    
    Specifies areas of interest; enables domain-specific mentor alignment.
    
- **Application Clarity (Where unclear / How unclear / Both unclear)**
    
    Distinguishes between informational and execution gaps.
    
- **Resume Preparedness (None / Basic / Strong)**
    
    Reflects readiness level; helps match with mentors who improved from similar starting points.
    

---

### **B. If Primary Focus = Courses / Academics**

- **Course Selection Clarity (Clear / Confused / Overloaded)**
    
    Indicates ability to plan academic workload.
    
- **Core Course Load Pressure (Low / Medium / High)**
    
    Reflects academic stress and difficulty level.
    

---

### **C. If Primary Focus = Career Direction**

- **Clarity of Career Path (None / Exploring / Clear)**
    
    Captures level of decision certainty. Matches with mentors who faced this 
    
- **Career Confusion Type (Core vs Non-core / Domain choice / Multiple interests)**
    
    Identifies the exact nature of the dilemma.
    

---

### **D. If Primary Focus = Skill Development**

- **Current Skill Focus (CP / Development / Core / Mixed / None)**
    
    Indicates current effort direction.
    
- **Consistency Level (Low / Medium / High)**
    
    Reflects execution and discipline in skill-building.
    

---

### **E. If Primary Focus = Exploration**

- **Interest Fields (list)**
    
    Captures areas of curiosity.
    
- **Interest Certainty Level (Low / Medium / High)**
    
    Indicates level of commitment.
    
- **Exposure Level (Not aware / Aware but not explored / Explored multiple options)**
    
    Differentiates between lack of exposure and active exploration
    

---

## **1.4 Third Year (Commitment Stage)**
The third year represents a phase where students must **finalize direction while simultaneously executing on internships and placements**. This stage is often characterized by high pressure due to overlapping timelines and expectations.

To handle this effectively, the schema follows a **conditional structure**, where deeper questions are triggered based on the student’s primary focus.

---

### **Step 1: Identify Primary Focus Area**

- Internship (ongoing / improvement / second intern)
- Placements
- Higher Studies
- Domain Clarification (not fully sure yet)

This ensures that the system focuses on the student’s most immediate concern and avoids unnecessary questioning.

---

### **Step 2: Base Fields (Applicable to All Students)**

- **Internship Domain Finalized (Yes / No / Partially)**
Captures clarity of direction; distinguishes between fully decided and still exploring students.
- **Internship Experience Quality (None / Poor / Average / Good)**
Reflects past outcomes; aligns with mentors who had similar success or setbacks.
- **Stress Level (Low / Medium / High)**
Captures pressure during this stage; helps match with mentors who handled similar stress.
- **Clarity of Long-Term Direction (Low / Medium / High)**
Indicates overall confidence in career path; aligns with mentors at similar clarity levels.

---

### **Step 3: Conditional Fields Based on Primary Focus**

---

### **A. If Primary Focus = Internship**

- **Current Internship Status (None / Ongoing / Completed)**
Captures present stage of internship engagement.
- **Internship Satisfaction (Low / Medium / High)**
Reflects whether the experience met expectations.
- **Internship Concern Type (multi-select)**
    - Want better internship
    - Not satisfied with domain
    - Want PPO
    - Confused about next steps
    
    Identifies specific concerns for targeted mentor matching.
    
- **Target Internship Domains (for next step)**
Enables alignment with mentors who transitioned or improved in similar domains.

---

### **B. If Primary Focus = Placements**

- **Placement Preparation Status (Not started / Preparing / Ready)**
Captures readiness level.
- **Target Roles (SDE / Consulting / Core / Research / Others)**
Specifies career goals; enables precise matching.
- **Preparation Strategy (CP / Development / Core subjects / Mixed)**
Indicates approach; aligns with mentors who followed similar strategies.
- **Company Awareness Level (Low / Medium / High)**
Reflects preparedness and research depth.
- **Placement Concern Type (multi-select)**
    - Not getting shortlisted
    - Weak in interviews
    - Resume issues
    - Confused about roles

---

### **C. If Primary Focus = Higher Studies**

- **Interest in Higher Studies (Exploring / Preparing / Confirmed)**
Captures commitment level.
- **Target Path (MS / MBA / Research / Others)**
Specifies direction.
- **Preparation Status (Not started / Preparing / Applied)**
Reflects progress.
- **Primary Concern**
    - Exams (GRE/GATE etc.)
    - Profile building
    - Decision clarity

---

### **D. If Primary Focus = Domain Clarification**

- **Domains Under Consideration (list)**
Captures current options.
- **Reason for Confusion**
    - Multiple interests
    - Lack of information
    - Fear of wrong choice
- **Decision Urgency (Immediate / Can explore)**
Reflects time pressure.

---

## **1.5 Fourth Year (Transition & Decision Finalization Stage)**

The fourth year represents the transition from academic life to professional or academic careers. Students at this stage face **final, high-stakes decisions** regarding job acceptance, domain switching, or higher studies.

To handle diverse scenarios effectively, the schema follows a **conditional structure**, where deeper questions are triggered based on the student’s primary situation.

---

### **Step 1: Identify Primary Situation**

- Have Job Offer
- No Job Offer
- Considering Higher Studies
- Considering Domain Switch

This ensures that the system focuses on the student’s immediate decision context.

---

### **Step 2: Base Fields (Applicable to All Students)**

- **Job Offer Status (No Offer / PPO / Placement Secured)**
Indicates current position; aligns with mentors who were in similar situations.
- **Offer Satisfaction Level (Low / Medium / High)**
Captures internal conflict regarding current offers; matches with mentors who reconsidered or accepted offers.
- **Domain Switch Interest (Yes / No / Considering)**
Reflects desire for change; aligns with mentors who switched or continued in the same domain.
- **Higher Studies Decision (Not Considering / Preparing / Confirmed)**
Indicates commitment toward further studies; matches with mentors who made similar decisions.
- **Primary Concern (Growth / Stability / Passion / Switching)**
Captures decision-driving factor; ensures mentor advice aligns with student priorities.

---

### **Step 3: Conditional Fields Based on Primary Situation**

---

### **A. If Primary Situation = Have Job Offer**

- **Offer Type (Core / Non-core / Consulting / Research / Other)**
Specifies domain of offer; enables domain-specific mentor matching.
- **Joining Clarity (Clear / Unsure / Considering alternatives)**
Captures commitment level toward the offer.
- **Concerns (multi-select)**
    - Not satisfied with role
    - Want better opportunity
    - Confused about long-term growth
    - Considering switch before joining

---

### **B. If Primary Situation = No Job Offer**

- **Placement Preparation Status (Not started / Preparing / Actively applying)**
Reflects current effort level.
- **Primary Issue (multi-select)**
    - Not getting shortlisted
    - Weak interview performance
    - Resume issues
    - Lack of direction
- **Target Roles (list)**
Specifies intended roles for focused matching.

---

### **C. If Primary Situation = Considering Higher Studies**

- **Target Path (MS / MBA / Research / Other)**
Specifies direction.
- **Preparation Status (Not started / Preparing / Applied)**
Indicates progress level.
- **Primary Concern**
    - Exams (GRE/GATE etc.)
    - Profile building
    - Decision clarity

---

### **D. If Primary Situation = Considering Domain Switch**

- **Current Domain**
Captures present trajectory.
- **Target Domain**
Specifies intended shift.
- **Reason for Switching**
    - Interest
    - Salary
    - Growth
    - Burnout**2. Mentor Schema**

Matches , the student with mentors who had similar domain shifts 

---

# 2. Mentor schema

The mentor schema captures the mentor’s **year-wise decision journey, context of decisions, confidence levels, and advising capability**, enabling precise matching with students facing similar dilemmas at similar stages.

## **2.1 Basic Context**

- **Graduation Year**
Indicates recency of experience; used as a relevance signal where more recent mentors are prioritized due to alignment with current opportunities, hiring patterns, and competition levels.
- **Branch**
Provides academic background; enables relatability with students from similar disciplines.
- **Current Role and Domain (specific)**
Represents final outcome; enables goal-oriented matching.
- **Personality Type (Introvert / Extrovert / Ambivert)  makes it easier to match with students which have similar personalities which helps the mentor understand the student better**

---

# **2.2 Year-wise Decision Mapping (Core Structure)**

Each mentor’s journey is structured into **year buckets (Y1–Y4)**, directly mirroring the student schema. All fields below are captured **within each year**, ensuring context-specific matching.

---

## **For Each Year (Y1, Y2, Y3, Y4), capture:**

---

### **Domains Considered (list)**

Represents all domains the mentor evaluated during that year; enables matching with students exploring similar options.

---

### **Exploration Stage per Domain (structured)**

For each domain:

- Researched
- Attempted
- Achieved
- Worked

Captures depth of engagement; distinguishes superficial interest from serious pursuit.

---

### **Primary Decision Faced (year-conditional )**

The valid options depend on the year:

- **Y1:** Clubs / Peer group / Exploration of interests
- **Y2:** Internship vs exploration / Core vs non-core
- **Y3:** Placement vs higher studies / Domain finalization
- **Y4:** Job vs higher studies / Domain switching

Encodes the exact dilemma at that stage; ensures alignment with student decision context.

---

### **Decision Taken (structured)**

Examples:

- Chose non-core over core
- Prioritized placements
- Chose higher studies
- Continued in same domain

Represents the final action taken.

---

### **Alternatives Considered (list)**

Captures competing options (e.g., “Consulting vs Software”); enables matching with students facing the same trade-offs.

---

### **Decision Confidence Level (Low / Medium / High)**

Indicates certainty at the time of decision.

**Matching contibution:**

- Low-confidence students are prioritized to match with mentors who had **low or medium confidence but achieved stable outcomes**, as they can better guide uncertain decision-making.
- High-confidence mentors are better matched to students who already have clarity and need validation.

---

### **Outcome Satisfaction (Low / Medium / High)**

Reflects long-term satisfaction with the decision.

**Matching Contribution:**

- Mentors with **high satisfaction** are prioritized for guidance on similar paths.
- Mentors with **low satisfaction** are valuable for cautionary guidance when students are considering the same decision.

---

### **Confusion Type Faced (mapped to student schema)**

- Indecision
- Lack of Information
- Overwhelmed
- Fear of Missing Out

Ensures direct compatibility with student confusion signals.

---

### **Problem Category Faced (multi-select)**

- Academic
- Career
- Personal
- Time Management
- FOMO

Captures the nature of the challenge within that year.

---

### **Struggles Faced (multi-select, year-specific)**

- Academic difficulty
- Rejections
- Time management
- Peer pressure

Anchored to the specific year, ensuring context-aware matching.

---

### **Mistakes Made (structured, year-specific)**

- Late start
- Wrong domain choice
- Overcommitment
- Lack of consistency

Allows matching with students facing similar stage-specific risks.

---

---

# **2.3 Internship-Specific Structure (Within Y2 & Y3)**

---

### **Internship Attempts (per year)**

- Did not apply
- Applied but not selected
- Secured internship

Captures effort-outcome relationship at the correct stage.

---

### **Internship Domain(s)**

Specifies domain(s) pursued.

---

### **Preparation Strategy (multi-select)**

- Competitive Programming
- Projects
- Core subjects
- Networking
- Resume-based

Captures preparation approach.

---

### **Internship Rejection Reason (if applicable)**

- Resume shortlisting issue
- Lack of preparation
- Interview performance
- Domain mismatch

Provides actionable insight for matching with similar student bottlenecks.

---

---

# 🔷 **2.4 Domain Switching Behavior**

---

### **Switched Domain (Yes / No)**

Indicates whether a transition occurred.

---

### **Switch Timing**

- During college
- After starting job

---

### **From Domain → To Domain**

Explicitly captures transition path.

---

### **Reason for Switching**

- Interest
- Salary
- Growth
- Burnout

---

---

# 🔷 **2.5 Mentoring Capability & Style**

---

### **Topics Comfortable Advising On (multi-select)**

- Internships
- Placements
- Higher studies
- Domain switching
- Skill development
- Time management

Ensures mentors are matched only in areas they feel confident advising on, improving quality of interaction.

---

### **Advising Confidence per Topic (Low / Medium / High)**

Captures self-assessed expertise in each topic.

**Matching Contribution:**

Mentors are prioritized when they have **high confidence in advising on the student’s problem area**, ensuring reliable guidance.

---

### **Mentoring Style (single-select)**

- Directive (gives clear recommendations)
- Facilitative (asks questions, helps student decide)
- Balanced

**Matching Contribution:**

- Introverted or uncertain students are matched with facilitative or balanced mentors.
- Students seeking clear answers are matched with directive mentors.

---

---

# 🔷 **2.6 Campus Involvement**

---

### **Clubs/PORs (with role level)**

- Member
- Coordinator
- Head

Captures leadership and engagement level

---

# **3. Cold Start Handling**

 The system handles these cases through **minimum viable feature extraction, fallback ranking rules, and feedback-driven refinement**.

---

## **3.1 New Student (No Prior Data)**

When a student has no prior interaction history, the system generates a minimal feature vector through a short onboarding:

- **Year**
- **Primary Problem Category**
- **Interest Fields**

---

### **Fallback Matching Strategy**

Mentors are ranked using the following deterministic rule:

1. **Stage Alignment Priority**
Mentors whose decision timeline (year-wise schema) aligns with the student’s current year are prioritized.
2. **Domain Overlap**
Mentors whose explored or current domains overlap with the student’s interest fields are ranked higher.
3. **Breadth of Experience Score**
Mentors who have explored multiple domains (higher number of domains considered across years) are prioritized, as they are better suited for ambiguous student contexts.
4. **Advising Confidence Filter**
Only mentors with medium/high advising confidence in the student’s problem category are considered.

---

### **Rationale**

This ensures that even with minimal input, the system surfaces mentors who:

- Have relevant stage experience
- Can handle ambiguity
- Are confident advising in that area

---

## **3.2 New Mentor (No Interaction History)**

When a mentor signs up, they are required to fill **structured schema fields** (year-wise decisions, domains explored, etc.), but lack performance history.

---

### **Matching Strategy**

- New mentors are **included in matching**, but with a **confidence weight penalty**
- They are only matched if:
    - They have **high advising confidence** in the relevant topic
    - Their **year-wise journey strongly aligns** with the student context
- They are **not excluded**, but are:
    - Less likely to appear at the top initially
    - Gradually promoted based on feedback

---

### **Rationale**

This avoids:

- Starving new mentors of opportunities
- Risking poor matches without validation

---

## **3.3 Both New (No Data on Either Side)**

When both student and mentor lack interaction history, the system relies entirely on **onboarding-derived minimal structure**.

---

### **Mandatory Onboarding (for both)**

Even in cold-cold scenarios, the system enforces:

- **Student:** Year, Problem Category, Interest Fields
- **Mentor:** Graduation Year, Current Domain, Topics Comfortable Advising On

This ensures a **minimum comparable feature space** exists.

---

### **Fallback Matching Strategy**

Mentors are ranked using:

1. **Year Proximity**
Mentors whose graduation year is closest to the student’s current year are prioritized.
2. **Domain Alignment**
Match between student interest fields and mentor current domain.
3. **Advising Topic Match**
Mentor must have declared confidence in the student’s problem category.
4. **Diversity** 
If multiple mentors are equally ranked, randomly select among top candidates to avoid bias concentration.

---

### **Rationale**

This ensures:

- Matching is still **structured, not random**
- No reliance on unavailable signals like ratings
- Fair exposure for new mentors

---

# 🔷 **3.4 Feedback Loop Design (Critical Component)**

The system continuously improves matching quality using post-interaction feedback.

---

## **Feedback Signals Collected**

After each session:

- **Student Rating (1–5)**
- **Mentor Rating (1–5)**
- **Session Helpfulness (Yes / No)**
- **Follow-up Interaction (Yes / No)**
- **Topic Tags Covered  etc ,**

---

## **How Feedback Updates Matching**

1. **Mentor Reliability Score**
Aggregated from ratings and helpfulness → increases ranking weight.
2. **Topic-Specific Confidence Adjustment**
If a mentor consistently receives high ratings in a topic, their advising confidence for that topic is increased.
3. **Mismatch Detection**
Low ratings trigger penalty for similar future matches with the same feature combination.
4. **Repeat Interaction Boost**
If a student returns to the same mentor, similar mentor profiles are boosted for future matches.

---

## **Rationale**

This creates a **closed feedback loop**, where:

- Good matches are reinforced
- Poor matches are gradually filtered out
- The system improves without manual intervention

---
