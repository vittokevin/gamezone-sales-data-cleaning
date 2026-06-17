# :loudspeaker:Gamezone Sales Data Cleaning

## Project Overview :exclamation::exclamation:
Stumbled across [Christine Jiang's video](https://www.youtube.com/watch?v=y9wFFD2bXQM) on data cleaning and it actually made a lot of things click. She lays out a 5-step framework called CLEAN, and I followed along using a fictional e-commerce dataset from a gaming company called GameZone — 20,000 rows of messy sales records with broken dates, blank values, duplicate orders, and weird shipping timestamps.

The goal was simple: take raw, disorganized data and get it to a point where it's actually trustworthy enough to analyze. Not perfect — just honest, documented, and ready to work with.

Good practice ground.

## :question: Assessment Objectives
The main goal here was to actually learn how data cleaning works in practice

Specifically, I wanted to:
1. Understand how to approach a messy dataset without panicking
2. Practice identifying what's fixable vs. what just needs to be documented and flagged
3. Build the habit of keeping a proper issues log throughout the process
4. Get comfortable making judgment calls on things like nulls, duplicates, and outliers — the way a real analyst would
5. Produce a dataset that's clean enough to analyze

## :computer: Tools and Technologies
- Excel

## :floppy_disk: Methodology
Methodology
The whole process followed Christine Jiang's CLEAN Framework — a 5-step approach to data cleaning that mirrors how analysts actually work on the job.

Step 1 — Conceptualize the Data
Before touching anything, I took a step back and figured out what I was actually looking at. Each row = one unique order. Key metric = USD price. Key dimensions = purchase date, product name, marketing channel, account creation method, and country code. Knowing this upfront made everything else easier to prioritize.

Step 2 — Locate Solvable Issues
Did a first pass through every column using filters to check distinct values. Documented everything that looked off into an issues log. Fixed what I could — inconsistent date formats, inconsistent product name spellings, blank marketing channels and account creation methods replaced with "Unknown", and nonsensical values in the regional lookup table.

Step 3 — Evaluate Unsolvable Issues
Some things just couldn't be fixed with the data available. Missing purchase timestamps, $0 transactions, missing country codes, and ~2,000 ship dates that came before the purchase date. Instead of deleting or guessing, I documented all of it — noted the magnitude of each issue and flagged it for transparency.

Step 4 — Augment the Data
Added new columns to make the dataset more useful for analysis — broken out purchase year, month, and week from the timestamp, calculated a time-to-ship column, and brought in the region from the lookup table using a VLOOKUP.

Step 5 — Note and Document
Finalized the issues log with resolution notes and the percentage of records affected for each problem found. This is the paper trail that shows the full cleaning process — what was fixed, what wasn't, and why.

## :collision: Key Insights 

### Perfect data isn't the goal
Going into this, I assumed the end goal was a spotless dataset. It's not. The real target is data that's good enough to analyze, share, and build on. Chasing perfection wastes time and can actually introduce more problems — like imputing values that end up adding bias instead of fixing anything.

### Duplicates existed but were low impact
145 duplicate order IDs were found across 20,000 records — less than 1%. Technically an issue, but not one worth acting on immediately without full business context. Deleting records before understanding why they exist is riskier than leaving them in and documenting them.

### Low magnitude issues don't always need fixing
Not every data problem needs a solution. If an issue affects less than roughly 20% of the data, it's often fine to document it, note the magnitude, and move on. The priority is transparency — making sure anyone who uses the dataset knows what's in it and what isn't perfect about it.

## :sparkles: Reflection
The biggest thing this project taught me was about documenting it.

Before this, I thought data cleaning was mostly about finding problems and correcting them. But going through the CLEAN framework made it clear that the issues log is just as valuable as the cleaned dataset itself. Every problem I found needed a decision — fix it, leave it, or flag it — and that decision needed to be written down with a reason attached. That's what separates someone who just cleans data from someone who actually thinks like an analyst.

It also made me realize how much trust documentation builds. If someone else picked up this dataset tomorrow, they wouldn't have to guess why certain values were left as-is or why blanks were replaced with "Unknown." The paper trail explains everything. That kind of transparency is what makes your work credible and your findings usable.

Honestly, documenting the things I couldn't fix felt just as important as the things I could. The shipping date issue, the $0 transactions, the missing country codes — none of those got resolved, but they all got recorded. And that's the point. You don't have to have all the answers. You just have to be upfront about what you know, what you don't, and what you did about it.

## :star: Future Improvements
This project was a first pass, and there's still room to grow from here.

Keep practicing data cleaning on different datasets
One dataset isn't enough to make it stick. The plan is to keep running through messy datasets across different industries, different structures, and different types of problems until the thought process behind cleaning becomes second nature.

Apply this to university assessments
The CLEAN framework and the mindset behind it are transferable to any dataset, not just e-commerce. Even when assignments don't require formal documentation, running through these steps mentally will lead to cleaner, more credible work.

Build the documentation habit early
Most uni assignments won't ask for an issues log. But doing it anyway, even in a simple form, builds a habit that will matter later on the job. The earlier that becomes a default part of the workflow, the better.

Use this as a foundation for the full analytics lifecycle
Data cleaning is just the start. The next step is taking this cleaned GameZone dataset and actually running an analysis on it, answering real business questions and practicing how to communicate findings clearly. That's where the work starts to connect end-to-end.
