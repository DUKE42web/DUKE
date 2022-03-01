# Day 2

**Description**

Notes:

Invalid form controls are visually indicated as invalid, but this state is not communicated programmatically. Assistive technology users may have difficulty determining which controls are invalid.

**Recommendation**

Set `aria-invalid="true"` on form fields that contain invalid data. This will ensure that the field is exposed to assistive technologies as an invalid field, and screen readers will announce this, for example, by announcing "invalid entry" as part of the field description. Once the field is valid, remove the `aria-invalid` attribute or set it to `false`.

Setting aria-invalid

`<label for="address">Address</label>`\
`<input id="address" type="text" aria-invalid="true">`

When an inline error message communicates specific information (e.g., beyond the fact that the field was left blank), use `aria-describedby` to associate the error message with the form field. Once the field is valid, remove the error message.

Setting `aria-describedby` to point to an error message

Email \<input id="email" type="email" aria-invalid="true" aria-describedby="email\_error"> \<p id="email\_error">Please enter a valid email address in the format name@example.com
