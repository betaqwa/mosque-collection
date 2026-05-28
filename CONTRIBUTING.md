# Contributing

Thank you for helping improve the accuracy and completeness of this dataset.

## Ways to Contribute

### Reporting Incorrect Data

If you find a masjid or surau with wrong coordinates, a misspelled name, incorrect postcode, or any other data error, please [open an issue](https://github.com/betaqwa/mosque-collection/issues) with:

- The name of the masjid/surau
- The state and city
- What is currently wrong
- The correct information (with a source if possible — e.g. Google Maps link, official website)

### Adding Missing Entries

If a masjid or surau is missing from the dataset, open an issue with:

- Name
- Type (`masjid` or `surau`)
- Full address
- State and postcode
- Coordinates (latitude/longitude) if known
- Whether Friday prayer is held (for masjid)

### Submitting a Pull Request

1. Fork this repository
2. Edit `masjid.json` or `surau.json` directly
3. Ensure your entry follows the existing field structure (see [README.md](README.md) for field definitions)
4. Keep the file sorted by `state` → `city` → `name`
5. Do not include an `id` field
6. Open a pull request with a short description of what was added or corrected

## Data Quality Guidelines

- **Name**: Use the official name as written on the signboard or JAKIM registry. Title case preferred.
- **Coordinates**: Must fall within the declared state's geographic boundary.
- **Postcode**: Must be a valid 5-digit Malaysian postcode for the declared state.
- **Phone**: Include country code if known (`+60...`), otherwise local format.
- **Null fields**: Leave a field as `null` rather than using placeholder text like "Tiada Maklumat" or "-".

## Code of Conduct

Be respectful. This dataset serves the Malaysian Muslim community and contributions should reflect that intent.
