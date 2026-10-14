# Airman Credential Compass

A recommendation engine that ranks civilian certifications for US Air Force and Air National Guard members. You enter your Air Force Specialty Code (AFSC), duty status, career goals, experience, and budget. It ranks the credentials that fit, shows the exam cost and who can pay for it, and explains every ranking.

Built as Project 1 for BANA 6780 AI for Business (CU Denver, Fall 2026): "Build a Recommendation Engine that Should Exist."

**Live:** https://airman-credential-compass.vercel.app

## Why it exists
AF COOL (Air Force Credentialing Opportunities On-Line) lists credentials by AFSC and funds them, but it doesn't rank them for a specific person. It doesn't weigh your goals, whether you meet the experience requirements yet, what you'd pay out of pocket on your current duty status, or which funding source applies. Guard members on drill status can't use AF COOL funding at all, and most tools don't tell them what to use instead.

## How recommendations are generated
Content-based filtering with cosine similarity.

1. Each credential is a feature vector over 10 features: 8 career tracks (aviation maintenance, avionics and electronics, IT and networking, cybersecurity, healthcare, project management, HR and admin, quality and logistics), "matches my AFSC" (1.0 if named in the official AF career field training plan, 0.8 if our inferred mapping), and "entry level."
2. Your profile becomes a vector on the same features. The AFSC weight comes from the stay-or-switch slider, and the entry-level weight comes from your years of experience.
3. Base score = cosine similarity between the two vectors.
4. Practical adjustments: experience prerequisites you don't meet yet, a required training course, and out-of-pocket cost against your budget after AF COOL funding.
5. Credentials you already hold are skipped (holding PMP also skips CAPM, PHR skips aPHR, Paramedic skips EMT). Credentials that build on one you hold get a 20% boost, with the reason shown: "issuer" when the issuer recommends the first one before the second (CompTIA A+ before Network+, Network+ before Security+), "usual next step" otherwise (CAPM to PMP, EMT to Paramedic).
6. Final score = round(100 x cosine x adjustments), capped at 100. The page shows the vectors and the math.

## Data
`data/credential_data.json` holds 21 credentials checked on 14 October 2026 against each issuer's official site (fee, prerequisites, URL), plus AF COOL, GI Bill test reimbursement, and FAA/JSAMTCC funding rules with sources. `data/credential_notes.md` lists everything that could not be verified. `data/avionics_data.json` and `data/avionics_notes.md` add the five current avionics AFSCs (2A0X1, 2A2X1, 2A3X4, 2A3X5, 2A9X4, from the 31 Oct 2025 Enlisted Classification Directory) and four avionics credentials (FCC GROL, ETA Avionics, IPC J-STD-001, IPC-A-610). IPC certifications are earned through a paid course at a licensed training center, and whether AF COOL covers that course is unclear, so the tool shows the course cost instead of $0. Four AFSC-to-credential links come from official AF career field education and training plans; the rest are marked "inferred, not from AF COOL." Fees change, so confirm on the issuer's page.

## Limitations
- AF COOL's own pages couldn't be reached during the build, so most AFSC mappings are inferred.
- Eleven AFSCs and 25 credentials. A real version would need the full AF COOL catalog.
- No live job-market data; job links open an Indeed search for the credential near your location.
- Funding rules are summarized from published fact sheets. The base education office has the final word.

## AI disclosure
Built with Claude (Anthropic). Claude researched and verified the dataset against official sources, wrote the page code, and helped design the scoring. The problem choice, the recommendation logic decisions, and the review are mine.

## Run it
It's one static HTML file. Open `index.html` in a browser, or deploy the folder to any static host.
