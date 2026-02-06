# Ilkal Co-operative Bank - i18n (Internationalization)

A centralized translation management repository for the Ilkal Co-operative Bank Angular UI application. Contains language-specific JSON translation files for multiple languages.

## 📁 Folder Structure

```
i18n/
├── en/                    # English translations
│   ├── common.json       # Common UI text, navigation, buttons, labels
│   ├── errors.json       # Error messages and validation text
│   └── messages.json     # Success, info, warning, and confirmation messages
├── hi/                    # Hindi translations
│   ├── common.json
│   ├── errors.json
│   └── messages.json
└── kn/                    # Kannada translations
    ├── common.json
    ├── errors.json
    └── messages.json
```

## 🌍 Supported Languages

- **en** - English
- **hi** - Hindi (ಹಿಂದಿ)
- **kn** - Kannada (ಕನ್ನಡ)

## 📄 File Categories

### common.json
Contains frequently used UI elements:
- Application title and name
- Navigation menu items
- Button labels (Submit, Cancel, Save, Delete, etc.)
- Form labels (Username, Email, Password, Amount, Date, Status)
- Common phrases (Loading, Welcome, Yes, No, OK, Required)

### errors.json
Contains error messages and validation text:
- Validation errors (required fields, email format, password strength)
- Authentication errors (invalid credentials, account locked, session expired)
- API errors (network error, server error, timeout)
- Generic error handling messages

### messages.json
Contains user feedback messages:
- Success messages (saved, deleted, created, updated, login, transfer)
- Info messages (no data, initializing, processing, syncing)
- Warning messages (unsaved changes, confirm delete, high transfer amounts)
- Confirmation messages (confirm action, confirm logout)

## 🔧 How to Edit Translations

### For Clients:
1. **Open the JSON file** you want to edit in a text editor (VS Code, Notepad++, etc.)
2. **Locate the key-value pair** you want to update
3. **Modify only the value** (the text after the colon), NOT the key
4. **Ensure valid JSON syntax**:
   - Keep double quotes around keys and values
   - Use commas to separate items (but not after the last item)
   - No trailing commas
5. **Save the file** with UTF-8 encoding

### Example Edit:
```json
// Before
"username": "Username"

// After
"username": "नाम दर्ज करें"
```

### Add New Translations:
If you need to add new text:
1. Decide which category file it belongs to (common, errors, or messages)
2. Add the new key-value pair in the same format
3. Update all language files (en, hi, kn) with the new key

Example:
```json
"account_number": "Account Number"
```

## 🔗 Integration with Angular App

The Angular app imports these translation files and uses them with i18n tools. Update this repository when:
- Adding new UI text in the application
- Fixing translation errors
- Adding support for new languages
- Updating existing translations

### How the App Accesses Translations:
```typescript
// Example: In your Angular component
import { TranslateService } from '@ngx-translate/core';

constructor(private translate: TranslateService) {}

translate.get('app.title').subscribe((res: string) => {
  console.log(res); // Output: "Ilkal Co-operative Bank"
});
```

## 📋 JSON Keys Naming Convention

- Use **lowercase** with **dot notation** for nested properties
- Structure: `category.subcategory.key`
- Examples:
  - `app.title`
  - `navigation.home`
  - `buttons.submit`
  - `auth.invalid_credentials`

## ✅ Quality Checklist

Before committing translations:
- [ ] All JSON files are valid (use JSONLint or similar)
- [ ] All keys exist in all language files (en, hi, kn)
- [ ] No text is hardcoded; use translation keys instead
- [ ] Translations are contextually accurate
- [ ] Special characters are properly encoded
- [ ] Placeholder text like `{{length}}` is preserved exactly

## 👥 Access & Permissions

This repository is maintained with controlled access:
- **Owners**: Can merge changes, manage access, and deploy
- **Clients/Editors**: Can create pull requests and suggest translations

### Workflow for Client Edits:
1. Clone or download the repository
2. Create a new branch for your changes: `git checkout -b feature/update-hindi-translations`
3. Edit the JSON files
4. Commit your changes: `git commit -m "Update Hindi translations for accounts section"`
5. Create a Pull Request for review
6. Wait for approval and merge

## 📝 Important Notes

- **Always maintain UTF-8 encoding** for special characters in Hindi and Kannada
- **Test in the Angular app** after updating translations
- **Keep consistency** across all language files for similar messages
- **Avoid external punctuation changes** unless necessary
- **Document breaking changes** if you restructure JSON keys

## 🚀 Deployment

After translations are updated:
1. Pull the latest from this repository in the Angular app
2. Run the Angular build process
3. Deploy as per your CI/CD pipeline

## 📧 Support

For translation requests or issues:
1. Create an issue in the repository
2. Provide context (which text, which language, why)
3. Include example usage if applicable

---

**Last Updated**: February 2026
**Repository**: ilkal-co-op-bank-i18n