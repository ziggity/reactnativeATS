# reactnativeATS

As a recruiter for the last 10 years, building an ATS (applicant tracking system) would be pretty fun and I could bring my insider knowledge to help human resources. The current products on the market are very cost-prohibitive.

This will involve several components, including user authentication, candidate management, job management, and search functionality. Some competitors are Greenhouse (a huge one, that does a lot of things pretty quickly and is cloud-based but very costly), workday (sorta functions ok but does more metrics and dashboards better than actual candidate management tools like Greenhouse), bambooHR, Lever,, workable, iCIMS (ancient one used by amazon, horribly slow, and archaic but has great SQL database to showcase metrics quickly), jobvite, bullhorn (mostly for job posting  and blasting emails out but has changed a lot recently), 

Here's a short game plan to build such a system using React Native: identify which one I want to cover (human resources focused or is it more analytics focused?) I’ll go with the recruiter user experience first, best for them, and add in dashboards later. So fast upload of resumes, quickly tagging to jobs, getting candidate setup with hacker rank test email sent out, @ sign to HM for chatting but can be just a short one-way message doesn’t need web sockets to keep an open dialogue. 

# Components we might need: 

Navigator to manage the screens - candidate view, job view, database search view, dashboard view (analytics), job creation view
HomeScreen
JobsScreen (tagged to each recruiter/ HM)
CandidateScreen (view detailed info on a specific candidate)
OfferScreen (generate an offer)
CandidateSearchScreen to display all candidates on the screen. Candidates are served up from MongoDB 
CandidateCard which displays the candidate resume info, status, interviewing history data, name and scores they received from such interviews. referral tag also.
JobDetailCard which shows the job image summary, name, and description, and allows the recruiter to add details to the job.
Login Modal

## UI design react native 

https://miro.com/app/board/uXjVNteLzoA=/?share_link_id=227117246078 

Here's the board I made it's a template but has some modifications to show what's happening: 

Basically, the user flow and UI will go like this: 

1. Clerk sign-in component (prebuilt 3rd party app free for 100k)

2. Homescreen of the user (can change depending on permissions but keeping it simple for now) Search bar at top - which is to find candidates, profile image on left corner top can click to edit your settings, and your dynamic dashboard is in middle of the screen, and on the bottom is a link to create  / import upload a resume for a candidate. 

3. Search from the home screen brings you to the results screen, showing a list of candidates who meet those criteria (full name match, or other skills-based search). Results are: Flatlist of images of candidates if available, or a quick summary. You can click on profiles to see further info and tag them to a job. 

4. Clicking on the dashboard (middle of the home screen) will send you to your personal dashboard, you can modify which metrics to track (time to fill your assigned jobs, total candidates in the pipeline, or total referrals processed within the SLA, any red alerts or yellow alerts that need your attention such as candidates in the job bucket but not yet moved forward (5 day warning if they are done taking the online test, they need to be pushed to phone screen with HM). 

5. Clicking on a candidate from the search results screen will take you to their profile. you can modify their resume and upload recent one, you can tag them to a job, and push them to the next stage (each candidate will be in a stage, (applicant, referral, phone screen 1, phone screen 2 (HM), take home test (if applicable), phone screen 3 (if required), onsite, debrief (notes from onsite meeting with stakeholders), offer stage (pending approvals and permissions of users can only see this step), hired final stage. 



6.  Clicking on a candidate's resume from the candidate screen brings up their current resumes and past resumes (can click one to highlight it to be the main focus and will only be visible to those tagged to this job.) User who created the job is a super user and can see all the details. HM can only see the most recent resume. 


## Installation


```bash
git clone ...
cd reactnativeATS
npm i 
npm start 
```

## Usage

for testing purposes and learning how to build an ATS

## Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[MIT](https://choosealicense.com/licenses/mit/)