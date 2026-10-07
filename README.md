# User Profile Form

A Java Swing desktop app built in NetBeans. The user fills in their profile details, optionally attaches a photo, and submits. Input is validated, a confirmation dialog shows the result, and the app then switches to a read-only view of the profile.

## Structure

```
src/
├── model/User.java                 Data class for the profile fields
└── ui/
    ├── MainJFrame.java             Main window, switches screens with CardLayout, entry point
    ├── RegistrationJPanel.java     Form, validation, photo upload
    └── ViewJPanel.java             Read-only display of the submitted profile
```

Each `ui/` class also has a matching `.form` file with the NetBeans Form Editor layout.

## Age

- Picking a date of birth fills in the age automatically (current year minus birth year, minus 1 if the birthday hasn't happened yet this year).
- On submit, the age in the spinner must match the age calculated from the date of birth. If not, a warning dialog shows the expected age.

## Validation

Checked on submit in order. The first failure shows an error dialog and focuses the offending field:

- First and last name required, letters plus spaces, apostrophes and hyphens only (max 50)
- Age between 1 and 120
- Date of birth required, and age must match it
- Email must be a valid address
- Gender must be selected
- Phone must match `123-456-7890`
- Continent must be selected

Hobbies and photo are optional.
