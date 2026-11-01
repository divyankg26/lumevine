# Release Notes:

## Today’s Focus and adaptive priorities

- Added a dedicated Today’s Focus card that immediately answers: “What would help me feel better today?”

- Added a primary daily action based on the user’s actual mood, sleep, hydration, and task data.

- Added compact wellness metrics for:

- Mood
- Sleep
- Water logged today
- Tasks completed today

- Fixed the oversized Today card and removed the unexplained empty space.

- Fixed Today buttons so they scroll to and focus the correct dashboard card.

- Fixed task counts so they only reflect today’s tasks.

- Added adaptive priority pools for:

- Missing mood
- Stressed mood
- Low mood
- Missing sleep
- Light sleep
- Water goals below target
- Open tasks
- Steady check-in days

- Fixed a bug where priorities incorrectly fell back to the generic message:

- “Keep following what feels supportive today.”

- Priorities now select directly from the correct data-aware pool.

- Added signal-based fallback priorities that reference the actual mood, sleep, water, and task data available.

- Removed hydration priorities when the user has not selected a personal water goal.

- Made priority selection deterministic so it does not feel randomly generated.

## Hydration fixes

- Fixed hydration totals incorrectly showing the same value everywhere, such as always showing seven cups.

- Changed daily hydration interpretation to use the latest log for that day, rather than adding multiple logs together.

- Fixed repeated logging behavior where entering five glasses twice displayed ten instead of the latest value.

- Updated Today’s Focus, hydration cards, graphs, trends, weekly summaries, and reflection calculations to use the latest daily entry.

- Fixed hydration percentages exceeding 100%, including values such as “1013%.”

- Removed ambiguous wording such as “10 Water logged.”

- Updated hydration wording to show clear values such as:

- “10 glasses”
- “10/12 glasses”
- “Not logged”

- Removed visible assumptions that every user has an eight-glass water goal.

- Added flexible wording when no personal hydration goal exists.

- Preserved older internal wellness scoring fallbacks where needed for compatibility.

## Password reset and account recovery

- Kept the existing two-minute password-reset cooldown.

- Added clear success feedback after the reset email is sent.

- Replaced the disappearing “Hang on, sending email…” state with a completed state such as “Reset email sent.”

- Improved reset-button state handling so users can understand what happened.

## Reminders

- Added Enter-key support when creating reminders.

- Fixed reminder feedback so it uses the selected time unit correctly:

- Seconds display seconds.
- Minutes display minutes.
- Hours display hours.

- Removed incorrect wording about a “daily limit” and daily reset behavior.

- Kept reminders active until they are completed or cleared.

- Updated reminder and missed-reminder messaging to be more supportive and less judgmental.

## AI Companion

- Fixed AI chat restoration so conversations open at the latest message instead of the beginning.

- Added support for remembering relevant previous conversations.

- Added bounded AI profile memory for:

- Goals
- Recurring struggles
- Preferences
- Progress notes
- Recent topics

- Added memory bootstrapping from recent conversations.

- Made AI responses adapt to previous context instead of treating every message as a new conversation.

- Added handling for messages such as:

- “I’m bored.”
- “I missed my routine.”
- “I’m doing better this week.”
- Short follow-up answers such as “good,” “great,” or “not good.”

- Added separate conversation pools for boredom and casual conversation.

- Added a joke response pool that produces jokes unrelated to wellness tracking.

- Added routine-missed response handling.

- Preserved existing AI routing and fallback behavior.

- Clear AI Chats and Clear All Data now also clear structured AI memory.

- Improved spacing between the AI Companion heading, clear button, and supporting text.

- Removed unnecessary emoji clutter from AI response bodies while keeping clear response labels.

## Weekly Snapshot and wellness reflection

- Added a clear button to Weekly Snapshot, matching the AI Companion card.

- Fixed Weekly Snapshot persistence so generated content does not disappear unexpectedly.

- Weekly Snapshot now respects its intended weekly reset behavior instead of randomly disappearing.

- Reworked awkward wording such as:

- “Many supportive moments”
- “Well supported”

- Updated wellness statuses to use clear, human language.

- Changed mood history display so the newest mood log appears first.

- Improved weekly reflection scorecards with clearer wording such as:

- “Hydration goal: met on X of Y days”
- “Sleep goal: met on X of Y days”
- “Task goal: met on X of Y days”

- Removed confusing wording such as “intention 8 glasses/day” when there is no personal hydration goal.

- Made pattern summaries tentative and user-friendly.

- Added contextual weekly observations connecting mood, sleep, hydration, tasks, and routines when enough data exists.

- Added explicit language explaining that patterns are observations, not proof that one habit caused another.

- Improved “Your Patterns” wording and removed awkward technical phrasing.

- Replaced decimal mood baselines such as “Neutral (3.93)” with categorical mood descriptions.

- Fixed hydration and mood graph labels so they remain understandable and cannot show impossible percentages.

- Added clearer descriptions for incomplete or limited data.

## Daily Routine

- Replaced the old personalized daily plan presentation with a dedicated Daily Routine card.

- Added actual morning-to-night activities such as:

- Wake-up
- Breakfast
- Pending tasks
- Breaks
- Movement
- Lunch
- Dinner
- Wind-down
- Bedtime

- Added routine generation, add, replace, and clear actions.

- Added routine persistence through Firebase so routines survive refreshes.

- Added a routine pool to avoid generating the exact same routine every time.

- Added data-aware routine generation when user data is available.

- Kept a fallback routine pool for users without enough data.

- Added custom activity creation.

- Fixed custom meal names such as breakfast, lunch, snacks, and dinner so they receive natural meal wording instead of “focused block” wording.

- Added routine-aware replacement options based on the current routine.

- Replaced system dropdowns with themed in-app pickers.

- Added time selection using the same special time-understanding format used by bedtime reminders.

- Added Previous, Cancel, Next, and Finish controls throughout routine editing flows.

- Disabled Previous on the first step rather than hiding it.

- Added welcome-guide-style progress indicators.

- Added a clear routine action that clears both the UI and Firebase data.

## Habit Journey, streaks, and recovery

- Fixed quest completion so completed quests provide their intended XP.

- Fixed progress displays that incorrectly remained at values such as 10/100 after quest completion.

- Streak and fire animation behavior now activates when progress reaches 100 XP, rather than requiring every quest to be completed.

- Increased the recovery bonus from 10 XP to 25 XP.

- Users can now reach 100 progress through:

- Three regular quests plus the recovery bonus, or
- Four regular quests without the bonus

- Made streak support useful instead of displaying only an availability message.

- Added persisted streak-shield behavior.

- Expanded quest pools and reduced duplicate quest categories.

- Made progress language supportive rather than demanding.

- Removed guilt-oriented streak-loss messaging.

- Made skipped days feel normal and recoverable.

## Authentication and account setup

- Prevented completed accounts from reopening username, password, or display-name setup after an offline reload or browser crash.

- Added local identity and setup-completion markers for offline resilience.

- Prevented failed profile reads from being interpreted as empty first-time profiles.

- Fixed Google setup reopening briefly after it had already completed.

- Added setup finalization locks to prevent duplicate setup flows.

- Added password visibility controls to:

- Email sign-in
- Email sign-up
- Google account setup

- Fixed display-name precedence when an email/password account later adds Google authentication.

- Google provider names no longer overwrite an existing Lumevine display name.

- Existing profiles do not re-enter Google setup unnecessarily.

- Preserved the normal first-time Google setup flow for genuinely new Google accounts.

- Added email verification enforcement to the email/password signup flow:

1. Create the account.
2. Send the verification email.
3. Store pending profile information.
4. Sign the user out.
5. Finalize the profile only after verified sign-in.

- Blocked unverified sessions from initializing the dashboard.

- Username availability validation now fails closed if the registry cannot be checked.

- Signup no longer continues as if validation succeeded when the username registry is unavailable.

- Improved handling of Firestore access errors so they are not silently treated as missing users.

- Fixed self-friend-request handling so it reports that users cannot send requests to themselves.

- Fixed valid usernames incorrectly returning “No account found.”

- Added single-flight protections for friend request accept, decline, and cancel operations.

- Added optimistic UI updates and rollback handling for friend requests, mood, sleep, gratitude, and welcome-guide actions.

- Firestore security rules were intentionally left unchanged to avoid introducing unrelated cascading issues.

## Themes and visual consistency

- Renamed themes:

- Burgundy → Orchid
- Nature → Moss
- Glacier → Mist

- Updated taglines:

- Orchid — Reflect
- Moss — Ground
- Mist — Restore

- Preserved compatibility with existing saved theme preferences.

- Expanded reset and countdown blue styling across all themes and cards, including:

- Patterns & Progress
- Weekly Snapshot
- Other cards that previously missed the reset styling

- Improved long card headings so wrapped second lines are indented beneath the heading text instead of appearing directly below the icon.

- Improved spacing in cards with long titles such as:

- Weekly Reflection + AI Coach
- Today’s Wellness Reflection
- Future Self Reflection

## Grocery Planning

- Expanded Grocery Planning beyond basic arithmetic.

- Added:

- Total plan cost
- Monthly amount
- Weekly target
- Daily guide
- Per-shopping-trip amount
- Buffer amount
- Estimated shopping trips

- Replaced the run-on result sentence with a structured summary layout.

- Aligned corresponding left and right result rows.

- Added responsive single-column behavior for smaller screens.

## Account, Help, and navigation

- Replaced “Bug Reporting” and “Report Now” with “Contact Support.”

- Added polished FAQ and About Us link cards under Account → Help.

- Added:

- [FAQ](<https://lumevine.runs-at.dev/faq/?utm_source=chatgpt.com>)
- [About Us](<https://lumevine.runs-at.dev/about-us/?utm_source=chatgpt.com>)

- Added smooth arrow-key scrolling support.

- Added touch scrolling to internal dashboard card and list containers.

- Improved scrolling behavior across long cards and conversations.

## Terms of Service

- Added a required “I have read the Terms of Service” checkbox.

- Users cannot accept the terms without checking the box.

- Unchecked acceptance now:

- Highlights the checkbox area.
- Shows an explanatory message.
- Focuses the checkbox for correction.

## Keyboard shortcuts

- Updated shortcut names and mappings to match the current card names.

- Added shortcuts for the newer dashboard structure.

- Updated Gentle Reminders to use `G+R` rather than the previous mapping.

- Updated card indices after adding Today’s Focus.

- Removed outdated wording such as:

- “Includes A Gentle Daily Rhythm, Weekly Snapshot, and Your Patterns.”

- Updated shortcut descriptions in the Account area and Welcome Guide.

## Import and export

- Import now restores the saved account theme.

- Export now includes the account theme.

- Existing theme keys remain compatible with the renamed theme labels.

## Performance and interaction feedback

- Made mood, sleep, gratitude, welcome-guide, and friend-request actions feel immediate.

- Added optimistic updates so the interface responds before slower persistence operations finish.

- Added rollback behavior when persistence fails.

- Added protections against duplicate requests caused by repeated clicks or race conditions.

- Improved loading and status feedback throughout account and wellness interactions.

## Supportive product language

- Removed guilt-inducing progress and streak messaging.

- Reframed tracking as optional and flexible.

- Made skipped routines and missed days feel recoverable.

- Replaced competitive friend-comparison wording with supportive language.

- Updated reminders, wellness summaries, missed-routine responses, and progress messages to celebrate consistency without demanding perfection.

- Kept pattern analysis tentative so the app helps users understand themselves without claiming unsupported cause-and-effect relationships.
