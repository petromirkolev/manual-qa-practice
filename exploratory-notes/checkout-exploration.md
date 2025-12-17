# Checkout Exploratory Testing Notes

## Environment

- Browser: Chrome Version 143.0.7499.147 (Official Build) (arm64)
- OS: macOS 15.7.1
- URL: https://shop.polymer-project.org/checkout
- Date: 2025-12-17

## Validation & UX

- After correcting an invalid email, the error message disappears only after clicking outside the field.
- The phone number validation error message (“Invalid phone number”) disappears when clicking inside the field, making it unclear whether the entered value is now valid.
- City field accepts numeric-only values.
- State/Province field accepts numeric-only values.
- Cardholder name field accepts numeric-only values.
- Credit cards with an expiry date before the current date are accepted.
- Email field accepts addresses in the format `latinChars@cyrillicChars`.

## Input Handling

- Address field accepts numeric-only values.
- Address field enforces a minimum length of 5 characters.

## Visual / Responsiveness

- Checkout page layout breaks at extremely small viewport widths (below ~150px).

## State & Flow

- No unexpected crashes observed during form interaction.
- Refreshing the page clears all entered data without warning.

## Open Questions / Risks

- Is clearing form data on page refresh expected behavior?
- Are numeric-only values for location and name fields acceptable per requirements?
