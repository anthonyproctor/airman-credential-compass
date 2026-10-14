# Credential dataset: uncertainty notes (checked 2026-10-14)

## Biggest gaps
1. **AF COOL itself couldn't be opened.** afvec.us.af.mil and myairforcebenefits.us.af.mil don't resolve from this network (NXDOMAIN, even through public DNS). cool.osd.mil/usaf returned Access Denied. So **no AFSC-to-credential mapping in the file comes from AF COOL.** Each mapping is one of two kinds:
   - from the official AF Career Field Education and Training Plan (CFETP) for that AFSC: FAA A&P for 2A3X3 and 2A6X1; NREMT and NRP for 4N0X1
   - marked "inferred, not from AF COOL" (all the rest)
2. **ANG eligibility wording.** The strongest wording I actually opened is the 460 FSS AF COOL trifold (PDF dated 2024-07-05): "ANG and AFRS must be on Title 10 or Title 32, Section (502)F Orders for entire duration of credential process." The official ANG fact sheet (serv=22) is quoted in search-engine extracts as also requiring "Service members on Title 32 orders must be eligible for Title 10 benefits or operating under Title 10 authority" and saying "Air National Guard Service members on Drill Status are not eligible." I couldn't open that page, so that wording is UNVERIFIED by direct read.
3. **The $4,500 lifetime cap** comes from a PDF copy of the official fact sheet (Active Duty version, review date 10 October 2024) hosted on guard.utah.gov. The 2024 trifold says the same. Both sources agree.
4. **What AF COOL covers is disputed.** The fact sheet lists exams, books (not to exceed $500), admin and application fees, and recertification. The 2024 trifold also lists "coursework, prep courses." Prep course coverage is UNVERIFIED.

## AFSC notes
- **3D0X2 and 3D1X2 are legacy codes.** All 3DXXX converted to 1D7XX Cyber Defense Operations effective Nov. 1, 2021 (ACC). airforce.com's ANG bonus list now shows "Information Technology/IT Systems (1D7X1)" with shreds A (Network Operations) and B (Systems Administration). Which shred each old code maps to is UNVERIFIED. I couldn't find a 1D7 CFETP.
- **3F0X1's official title** is "Human Resources and Administration" (CFETP dated 18 March 2026), not "Personnel/Force Support."
- **The 4N0X1 CFETP is dated 24 July 2020.** A newer edition may exist.

## UNVERIFIED credential fields
- FAA A&P fee: knowledge test prices are set by the testing centers (PSI), and FAA doesn't publish them. Guard members can take the knowledge tests free through JSAMTCC. Designated Mechanic Examiner oral and practical fees are UNVERIFIED.
- Microsoft AZ-104 fee: the official page says the price depends on country, and no US figure was shown.
- NCATT AET eligibility and typical roles.
- NREMT EMT age and course-recency rules.
- NCLEX-PN eligibility (set by each state board) and state licensure fees.
- `typical_roles` for CQI, CSSGB, NREMT EMT and NRP, NCLEX-PN, CCMA, CPT, aPHR, PHR, CAPM and PMP: the issuer pages I read didn't list roles. I left these UNVERIFIED instead of guessing.
- Army Credentialing Assistance as an ANG funding source and state Guard benefits weren't researched.

## Smaller caveats
- SHRM military fees: the pairing of member and nonmember columns is inferred from the table layout and the $49 standard-deadline difference ($320/$420 early bird, $369/$469 standard).
- PMP: I read the "5 years" tier line, but the "secondary diploma" label for that tier is inferred.
- ASQ CSSGB: the page I read says 3 years of experience is required and no waivers are granted. Older versions of the program had no experience requirement, so re-check.
- CompTIA Security+ V8 is expected around Nov 17, 2026, so the $439 V7 price may change.
- NCLEX registration fee goes from $200 to $350 for registrations on or after Feb 1, 2027.
- Prices are list prices. Retake bundles and member discounts are noted where the source showed them.
