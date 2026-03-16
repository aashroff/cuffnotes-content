# Contributing to CuffNotes Content

Thank you for helping improve CuffNotes! This guide explains how to add
or edit flashcard content.

## You do NOT need any coding tools

All content is in JSON files. You can edit them directly on GitHub using
the web editor. No Flutter, Dart, or terminal needed.

## How to contribute

1. **Fork** this repository (click the Fork button at top-right)
2. **Navigate** to the file you want to edit in `content/`
3. **Click the pencil icon** to edit in your browser
4. **Make your changes** following the format below
5. **Click "Propose changes"** at the bottom
6. **Open a Pull Request** against the `main` branch

## Card format

Each card in a topic JSON file looks like this:

```json
{
  "id": "t25",
  "question": "Your question here?",
  "answer": "The answer text here.",
  "statute": "Act Name, s.X",
  "subcategory": "Must match one from subcategories list",
  "difficulty": 2,
  "tags": ["optional", "tags"]
}
```

### Rules

- **id**: Must be unique across the whole file. Use the topic prefix + number (e.g. t25, as01, po23)
- **question**: The prompt shown on the front of the flashcard
- **answer**: The answer shown on the back. Be accurate and cite case law where relevant.
- **statute**: The Act and section reference
- **subcategory**: Must exactly match one of the subcategories listed at the top of the file
- **difficulty**: 1 (basic), 2 (intermediate), or 3 (advanced)
- **tags**: Optional array of keywords for search
- **version**: When you add cards to a file, increment the version number at the top of the file by 1

### Quality guidelines

- Check the statute reference is correct
- Use the official wording from the Act where possible
- Include case law references (e.g. R v Gomez) where they clarify the law
- Keep answers factual, not opinions
- If adding a new subcategory, add it to both the subcategories array AND the card's subcategory field

## Adding a new topic

To add an entirely new legislation area (e.g. Misuse of Drugs Act):

1. Create a new file in `content/` (e.g. `drugs.json`)
2. Follow the same structure as existing files
3. The app will automatically pick it up once merged

## Automated validation

A GitHub Action automatically checks your JSON when you open a PR.
If it fails, check that your JSON is valid and matches the schema.
