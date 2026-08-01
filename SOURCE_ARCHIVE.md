# Google AI Studio Source Archive

The complete sanitised Google AI Studio export is stored at:

`source/colouring-book-creator-sanitized.zip`

The archive contains the React, TypeScript, Node/Express, DataForSEO integration, PDF generation utilities, and automated tests exported from Google AI Studio.

## Security review

Before upload:

- no live API credentials were found in the exported source
- `.env.example` contains empty placeholders only
- the project package name was updated to `ai-book-creator-market-research`
- the portfolio README and repository `.gitignore` were preserved

## Extract locally

```bash
unzip source/colouring-book-creator-sanitized.zip -d app
cd app
npm install
npm test
npm run dev
```

The source will be expanded into the repository root during the next local-development migration to Antigravity or another Git-enabled development environment.
