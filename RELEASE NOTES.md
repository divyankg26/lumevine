# Release Notes:

AI Companion and routine guidance

- Fixed boredom messages being mistaken for answers to the opening check-in. Messages such as “I’m bored” and “nothing to do” now reach a relevant response.

- Added a one-hour cooldown for water suggestions after a water log. The wellness card refreshes immediately and avoids repeating water prompts during the cooldown.

- Updated the AI to recognize varied questions about what to do now or what comes next. It checks the saved routine against local time, identifies the current or next activity, and treats unscheduled time as open rather than something that must be filled.

- Added gentle alternatives for schedule gaps and days without a routine, including the option to rest or leave the time unplanned.

Wellbeing recommendations

- Made suggestions responsive to mood and task load, rather than treating missing check-ins or unfinished tracker goals as evidence that something is wrong.

- Reviewed public wellbeing guidance and updated relevant suggestions and FAQ explanations. Recommendations remain optional and are not presented as diagnosis or treatment.

- Revised sleep guidance to avoid arbitrary thresholds and reduced advice that treated tracker goals as health requirements.

- Removed arbitrary priority scoring, forced follow-up plans, and a fabricated confidence score.

- Adjusted routine suggestions to avoid overloading the day with tasks, mandatory water breaks, or instructions to finish everything.

Signup, dashboard, friends, and streaks

- Fixed signup theme selection so previews or delayed profile reads do not override the selected theme.

- Corrected friend lookup so an invalid dotted username such as `alex.y` does not match `alexy`.

- Kept dashboard cards hidden until startup data is ready, preventing incomplete cards from appearing before the loading state.

- Made friend-request Accept and Decline actions wait for Firestore operations. Both actions remain disabled while processing; the request stays visible, the Accounts panel remains open, and failed actions can be retried.

- Softened streak messaging and clarified that a reset changes the count, not the user’s recorded check-ins.

Privacy and help information

- Updated the Privacy Policy to explain that the AI Companion uses in-app, rules-based responses rather than an external generative AI provider.

- Clarified that chat history may be stored in Firebase for app features and is not used to train AI models.

- Added a plain-language overview of Firebase access controls without publishing the deployed security rules.

- Explained cloud encryption at rest while distinguishing it from browser storage.

- Stated that the Firebase data region and Lumevine-specific independent audit status are unconfirmed, rather than guessing.

- Expanded help content on wellbeing recommendations, data storage and controls, export and deletion, medical limitations, and support.

Website and app experience

- Created a landing page at `/`; there was no landing page before this work. The app remains at `/app/`, with About and Privacy pages at `/about/` and `/privacy/`.

- Added page descriptions and canonical metadata, and updated navigation to use the new routes.

- Removed fabricated app previews so the landing page does not imply that mockups represent the actual app. Added a contained pastel botanical accent instead.

- Refined the landing page’s pastel styling, feature sections, and closing call to action.

- Fixed local preview styling so the page’s assets load when served from the repository’s `docs` directory.

- Updated site links to open the public website rather than local files.

- Fixed the “See how it works” anchor behavior: clicking it still scrolls to the section, while refreshing returns the page to the top.

- Added a local-time greeting in the app using the AI-preferred name when available, otherwise the display name. The greeting is cursive and left-aligned while the Lumevine title and subtitle remain centered.

- Added a slowly drifting pastel blob beside the plant and a separate, more visible green blob behind the landing-page headline. Both respect reduced-motion settings.

- Removed the legacy `about-us` and `privacy-policy` directories. The canonical `/about/` and `/privacy/` pages remain.
