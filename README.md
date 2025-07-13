```markdown
# US Phone Number Validator

A JavaScript function to validate US phone numbers in various formats. The validator checks whether a given string matches valid US phone number patterns, including optional country code, parentheses, spaces, and dashes.

---

## Features

- Validates multiple US phone number formats:
  - `555-555-5555`
  - `(555)555-5555`
  - `(555) 555-5555`
  - `555 555 5555`
  - `5555555555`
  - `1 555 555 5555`
  - `1 (555) 555-5555`
- Ensures the area code is present and valid.
- Checks if the country code, if provided, is exactly `1`.
- Rejects invalid formats and numbers with incorrect characters.

---

## Usage

### Function

```js
function telephoneCheck(str) {
  const regex = /^(1\s?)?(\(\d{3}\)|\d{3})[\s-]?\d{3}[\s-]?\d{4}$/;
  return regex.test(str);
}
``

### Examples

```js
console.log(telephoneCheck("555-555-5555")); // true
console.log(telephoneCheck("1 555-555-5555")); // true
console.log(telephoneCheck("(555)555-5555")); // true
console.log(telephoneCheck("5555555555")); // true
console.log(telephoneCheck("555-5555")); // false
``

---

## Testing

You can test various phone number formats to verify the validator:

```js
console.log(telephoneCheck("1 (555) 555-5555")); // true
console.log(telephoneCheck("(6054756961)")); // false
console.log(telephoneCheck("123**&!!asdf#")); // false
console.log(telephoneCheck("555-5555")); // false
// Add more test cases as needed
``

---

## Implementation Details

The validator uses a regular expression that matches the following criteria:

- Optional country code `1` at the start, with optional space.
- Area code either in parentheses `(xxx)` or as three digits `xxx`.
- Optional separators (space or dash) between parts.
- Followed by three digits and four digits for the main number.

This ensures flexibility while maintaining validation accuracy for US phone numbers.

---

## License

This project is for educational purposes. Feel free to contribute or modify as needed.

---

## Contact

For questions or feedback, please contact [Your Name] at [your.email@example.com]

```
