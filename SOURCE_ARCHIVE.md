# Latest Google AI Studio source archive

The latest sanitised source export is stored at:

`source/ai-book-creator-market-research-v3-sanitized.zip`

This v3 archive contains the current React/TypeScript frontend, Node/Express backend, Amazon research integration, Cloudflare image-generation route, KDP pricing and page-calculation utilities, separated interior and cover PDF generation, ZIP packaging, and the automated test suite.

## Included v3 improvements

- Amazon KDP Production Mode defaults to 14 generated content pages
- live Book Page Calculator using the deterministic KDP page structure
- 24-page minimum validation applied only to the interior manuscript
- separate front cover, back cover and full-wrap cover assets
- KDP spine-width and spine-text eligibility rules
- UK and US KDP printing-cost and royalty calculations
- separate interior PDF and one-page full-wrap cover PDF
- complete KDP download ZIP package
- optional Amazon market research controlled by the settings toggle
- 202 automated assertions reported passing in Google AI Studio

## Security review

Before committing this archive:

- no live API credentials or token-like secrets were detected
- `.env.example` contains placeholders only
- DataForSEO, Gemini, Firecrawl and Cloudflare credentials remain server-side
- generated customer books and private research outputs are not included

## Local validation

The source archive passed a TypeScript/TSX syntax scan across 23 source files in the repository-preparation environment.

A full dependency install, test run and production build could not be repeated in that environment because its internal npm mirror did not contain `@google/genai@^2.4.0`. The uploaded project reports 202 passing automated assertions in Google AI Studio. Run the following in a normal npm environment before deployment:

```bash
unzip source/ai-book-creator-market-research-v3-sanitized.zip -d app
cd app
npm install
npm run lint
npm test
npm run build
```
