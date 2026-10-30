# The Art of IT Management

## Strategies, Techniques, and Leadership

---

*For the manager who inherited the system nobody documented, the budget nobody explained, and the team nobody thanked.*

---

## Preface

Most IT managers are promoted for technical excellence and then judged on everything except technical excellence.

The engineer who untangles a failing integration at two in the morning is rewarded with a team. The analyst who rescues a project is handed a portfolio. The service desk lead who holds a department together is made responsible for a budget, a vendor contract, an audit finding, and a board paper — usually in the same quarter, usually without training.

The skills that earned the promotion are necessary but not sufficient. What follows is a different discipline: choosing what not to build, explaining a trade-off to a CFO in her own language, deciding how much risk is acceptable, keeping a vendor honest, and building a team that performs when you are not in the room.

This book is about that discipline.

It is written for the manager in the middle: senior enough to be accountable for outcomes, junior enough to still be close to the work. It assumes you have some technical grounding and almost no formal management education. It assumes your calendar is full and your reading time is short. It tries, therefore, to be dense with usable material and light on inspiration.

Three commitments shape the book.

**First, practice over theory.** Every framework here is paired with a procedure, a template, and an example. If a chapter does not change what you do on Monday, it has failed.

**Second, honesty over certainty.** Management is a domain of trade-offs, not solutions. Where the evidence is contested — whether to centralize or federate, how far to scale agile, whether to outsource — the book says so and gives you the questions that resolve the choice in your context.

**Third, the whole job.** IT management is not one skill repeated. It is strategy, governance, delivery, risk, money, and people, held in tension. A manager who is excellent at delivery and blind to governance will eventually deliver something the organization cannot accept. A manager who governs beautifully and cannot ship will preside over a well-documented decline.

### What this book will not do

It will not turn you into a CIO in twenty-two chapters. It will not settle debates that depend on your industry, your regulator, and your chief executive. It will not replace the two things no book can supply: experience, and a mentor who will tell you the truth.

It will give you the vocabulary, the structures, and the questions. The judgment is yours.

---

## How to use this book

### If you have one week

Read the opening scenario and the "Key takeaways" of each chapter, then work through the checklists in Part VII. You will get a diagnostic of where your practice is thin. Come back for the chapters that match.

### If you are newly appointed

Read Part I and Part VII first. Chapter 22 contains a ninety-day plan that sequences the rest. Then read the part that matches your most urgent exposure — usually delivery (Part III) or risk (Part IV).

### If you are experienced

Use the book as a reference and a checklist. The step-by-step methods in each chapter are designed to be lifted directly into a workshop. The template library in Appendix A is designed to be copied, not admired.

### If you teach

Each chapter ends with discussion questions and a case. The eight-part structure maps to a ninety-minute session: objectives, scenario, concepts, method, case, exercise, pitfalls, close. The Meridian thread allows a semester-long simulation in which each week's decision constrains the next.

### Reading paths

| Your situation | Path |
|---|---|
| First management role | 1 → 2 → 19 → 7 → 22 |
| Running a delivery function | 7 → 8 → 9 → 15 → 20 |
| Inherited a security or audit finding | 10 → 11 → 12 → 4 |
| Asked to lead transformation | 3 → 16 → 17 → 18 → 21 |
| Preparing for a CIO interview | 2 → 3 → 4 → 13 → 15 → 22 |
| Business leader wanting visibility | 1 → 4 → 13 → 15 |

### A note on the numbers

Figures in this book are illustrative unless attributed. Where a real organization's results are cited, the source is named in the chapter's further reading. Do not lift a benchmark from this book into a board paper without checking it against your own data; benchmarks are conversation starters, not evidence.

---

## The Meridian Group case

Meridian is a fictional company. It is a composite of dozens of real organizations, assembled so that the problems in this book arrive in a realistic order and with realistic constraints. Nothing about it is designed to be easy.

### The company

**Meridian Group** is a 4,500-person holding company headquartered in a mid-sized European city, with operations in three divisions:

| Division | What it does | Revenue share | IT posture |
|---|---|---|---|
| **Meridian Financial Services** | Consumer lending, insurance brokerage | 45% | Highly regulated; core banking platform from 2009; quarterly regulatory reporting |
| **Meridian Logistics** | Regional freight, warehousing, last-mile delivery | 35% | Operational technology in warehouses; 140 drivers on mobile apps; thin margins |
| **Meridian Retail** | 180 stores and an e-commerce channel | 20% | Legacy POS estate; fast-growing online channel; seasonal peaks |

Group revenue is approximately €1.4 billion. EBITDA margin is 9%, below the sector median. The board has set a three-year goal: **grow online revenue to 30% of retail sales, cut logistics cost per parcel by 12%, and reduce group operating cost by €40 million.**

### The IT function

- 90 employees: 38 in infrastructure and operations, 22 in applications, 14 in data and reporting, 8 in security, 8 in the PMO and business partnering.
- Roughly 30% of application spend goes to vendors and managed services.
- IT operating spend is €58 million, about 4.1% of revenue; capital spend is €11 million.
- A cloud migration began two years ago. Twenty percent of workloads have moved. The business case assumed 40% by now.
- There is no formal IT strategy document. There is a three-year technology roadmap, last updated eighteen months ago, which the board has never seen.
- The risk register exists. It has 212 entries, most of them unowned.
- The security team has one certified incident responder and no tested recovery plan for the core banking platform.

### The people

**Priya Raman — Group IT Director.** Appointed nine months ago, internally promoted from Head of Applications. Technically strong, trusted by her team, still learning to operate at board level. She reports to the Group CFO, **Marcus Feld**, because the CIO role was eliminated in a cost programme four years ago and never reinstated.

**Marcus Feld — Group CFO.** Numerate, impatient, privately convinced that IT is a cost centre with poor cost transparency. He is not hostile to technology; he is hostile to unquantified claims.

**Elena Voss — CEO.** Three years into a turnaround. Wants digital growth, dislikes long presentations, asks "what does it cost and when will I see it?"

**Tomás Ferreira — Divisional Director, Logistics.** Runs the most operationally complex division. Believes group IT slows him down. Has bought three SaaS tools without telling anyone.

**Dr. Aisha Bello — Head of Risk and Compliance.** Former regulator. Calm, precise, and the person who will decide whether Priya's proposals survive committee.

**Jonas Weber — Head of Infrastructure and Operations.** Twenty-two years at Meridian. Deeply knowledgeable, change-averse, and the single point of failure for the core banking platform's batch schedule.

**Sofia Marchetti — Head of Security.** Hired eighteen months ago. Competent, under-resourced, and increasingly vocal about the gap between the board's appetite for digital growth and its investment in defence.

**Ravi Desai — Head of Data.** New. Enthusiastic. Has been asked to deliver an AI pilot before the data foundations exist.

### The arc

Each chapter advances Meridian by one decision:

| Part | What Meridian does |
|---|---|
| I | Priya clarifies her role, learns the business, and writes the first real IT strategy |
| II | The group designs governance, an operating model, and a service management capability |
| III | Meridian builds a delivery system and a funded portfolio |
| IV | A near-miss forces a serious approach to risk, security, and resilience |
| V | IT learns to budget, account for its assets, and prove its value |
| VI | Transformation, data, AI, and cloud become a coherent programme |
| VII | Priya builds a leadership team, manages the board, and plans her own succession |

### How to use Meridian

Treat it as a sandbox. Before reading a chapter's method, decide what you would do in Priya's position. Then compare. The gap between your instinct and the method is the most useful thing in the chapter.

---

## Book map

| Part | Chapter | Core question |
|---|---|---|
| **I. Foundations** | 1. The Evolving Role of the IT Manager | What am I actually accountable for? |
| | 2. Understanding the Business | How does this company make money, and where does IT touch it? |
| | 3. IT Strategy and Strategic Planning | What will we do, what will we not do, and how will we know? |
| **II. Governance and Organization** | 4. IT Governance | Who decides, who is accountable, and how is that enforced? |
| | 5. Operating Models and Organizational Design | How should IT be structured to deliver? |
| | 6. Policy, Process, and Service Management | How does work flow reliably, day after day? |
| **III. Delivery** | 7. Project Management Essentials | How do we deliver change on purpose? |
| | 8. Agile and Modern Delivery | How do we deliver change continuously? |
| | 9. Portfolio, Program, and Vendor Management | How do we choose, sequence, and source the work? |
| **IV. Risk, Security, and Resilience** | 10. Risk Management | How much risk are we carrying, and is that acceptable? |
| | 11. Cybersecurity Leadership | How do we defend, detect, respond, and recover? |
| | 12. Business Continuity and Disaster Recovery | What happens when it all stops? |
| **V. Financials and Value** | 13. IT Budgeting and Financial Management | What does IT cost, and what is it worth? |
| | 14. Asset, Licence, and Contract Management | What do we own, what do we owe, and what are we paying for? |
| | 15. Measuring and Communicating IT Value | How do we prove and explain value? |
| **VI. Transformation and Innovation** | 16. Digital Transformation | How does an organization actually change? |
| | 17. Data, AI, and Emerging Technology | How do we turn data into capability without creating new risk? |
| | 18. Cloud and Platform Strategy | What should we run, where, and on what foundation? |
| **VII. People and Leadership** | 19. Leading and Developing IT Teams | How do I build people who outperform me? |
| | 20. Influence and Stakeholder Management | How do I get things done without authority? |
| | 21. Change Leadership and Culture | Why do good changes fail, and what prevents it? |
| | 22. The IT Manager's Playbook | What do I do in the first ninety days, and after? |

---

*Part I begins with the question every IT manager answers badly at least once: what is this job, really?*
