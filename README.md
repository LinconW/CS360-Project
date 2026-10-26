# Stockroom — Lincon Woodruff — CS 360 Project Two

Native Android Java + XML UI for Project One Option 1: Inventory.

## Open and run
1. Extract this ZIP. In Android Studio select Open and choose the Stockroom folder (the folder containing settings.gradle).
2. Allow Gradle sync. Use JDK 17 or Android Studio's compatible embedded JDK. Install Android SDK Platform 35 if prompted. AGP 8.7.3 and Gradle 8.9 are pinned.
3. Run the app on an Android 6.0 (API 23) or newer emulator/device.
4. Enter any nonempty username and password to explore the UI. This does not authenticate or create a real account.
5. Edit each screen visually under app/src/main/res/layout using Android Studio's Layout Editor.

## Scope
Four scrollable XML screens: login/create account; inventory grid; add/edit; SMS permission settings. The inventory uses a TableLayout with labeled columns and horizontal scrolling, a grid alternative to the proposal's optional RecyclerView. Every record has increase, decrease, edit and delete controls. Deletion requires confirmation. Required-field, unique-identifier and nonnegative-quantity validation are included as UI feedback.

Records live only in preview memory, with instance-state restoration for rotation. No SQLite, real authentication, or SMS sending is implemented. SMS runtime permission requests and status are real; the alert button only previews a message. The phone field is a UI placeholder and is not saved. Project Three should implement account/database storage, phone preference persistence, and a permission-guarded SMS alert when quantity transitions to zero. This submission never sends messages or stores credentials.

## Rubric review
- Login: username, masked password, Log in, Create account.
- Data: labeled grid, sample records, Add item, Delete on every row, quantity controls, add/edit fields.
- SMS: optional telephony manifest declaration, SEND_SMS permission, runtime check/request, granted/denied UI, and continued inventory access after denial.
- Hierarchy: forest-green actions, light neutral background, clear titles, labeled inputs, 48dp+ controls, text stock statuses, consistent back/cancel paths.

## Manual check before submission
- Launch and verify the password is obscured; empty credentials show field errors.
- Navigate through every screen in portrait and landscape.
- Add/edit/delete temporary records; check empty and duplicate IDs, zero and invalid quantities.
- Decrease to zero and verify Out of stock text and disabled decrease.
- Deny SMS and return to inventory; grant through the system dialog/settings and check status updates.
- Preview an alert: no SMS should be sent.
- Try a small screen and large font; scroll forms and inventory horizontally as needed.

## Validation in creation environment
XML syntax and resource references checked. Android SDK/emulator unavailable in the creation environment; APK compilation and on-device visual/runtime verification must be completed in Android Studio before submission.

## Android references
https://developer.android.com/training/permissions/requesting
https://developer.android.com/guide/topics/manifest/uses-feature-element
https://developer.android.com/build/releases/agp-8-7-0-release-notes
