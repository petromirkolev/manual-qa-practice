1. **Empty cart handling**: Checkout prevents access or shows a clear “cart empty” path.
2. **Successful checkout**: User can place an order with valid required data.
3. **Required field validation**: Missing required fields block submission with clear errors.
4. **Email format validation**: Invalid email is rejected (if email exists).
5. **Postal/phone format validation**: Invalid postal/phone is rejected (if present).
6. **Whitespace handling**: Leading/trailing spaces in inputs don’t cause false failures.
7. **Order summary stability**: Items/totals shown match the cart and don’t change unexpectedly.
8. **State persistence**: Refresh/back navigation preserves expected state.
9. **Usability basics**: Error messages are specific and page remains responsive during submission.
