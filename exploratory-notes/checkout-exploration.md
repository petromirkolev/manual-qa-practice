# Checkout Exploratory Testing Notes

## Environment

- Browser: Chrome Version 143.0.7499.147 (Official Build) (arm64)
- OS: macOS 15.7.1
- Date: 2025-17-12

“After correcting invalid email, error message disappears only after clicking outside the field.”

## Observations

- Checkout page passes basic/common test cases but fails on multiple edge cases.

## Validation & UX

- "Invalid Phone Number" error message disappears when clicking in the phone number box which makes it impossible to tell if the provided phone number is valid.
- "City" field accepts numerical only values.
- Credit cards with expiry date before the current date are accepted.
- "State/Province" field accepts numerical only values.
- "Address" field accepts numerical only values.
- "Address" field accepts only >= 5 symbols.
- "Cardholder name" accepts numerical only values.
- Checkout page layout breaks in screen resolution < 150px wide.
- Email field accepts emails in the following format: latinChars@cyrilicChars.

## State & Flow

## Open Questions
