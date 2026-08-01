# AI Book Creator & Market Research Platform

An AI-powered publishing workflow that combines **Amazon market research**, **demand and competition analysis**, **original niche discovery**, **book concept development**, and **print-ready Amazon KDP production**.

The current implementation focuses on children’s colouring books, while the architecture and repository name are intentionally broader to support additional book formats in future.

> **Project status:** Active private development. The application is being refined, tested, and prepared for a future portfolio release.

---

## The problem

Creating a commercially viable book involves much more than generating pages.

A publisher must first answer questions such as:

- Are customers actively buying this type of book?
- What price range do customers appear willing to accept?
- How many pages do successful competing books commonly provide?
- Is the niche dominated by established competitors?
- Is there room for a differentiated, original concept?
- Should the publisher compete directly with popular titles or target an underserved market gap?

Most AI book-generation tools begin with a prompt and jump straight to content creation. This project adds the missing business layer: **evidence-led niche selection before production begins**.

---

## The solution

The platform follows a four-stage workflow:

1. **Research the market**  
   Search Amazon US or UK through DataForSEO, or explore wider web trends through Firecrawl.

2. **Evaluate the opportunity**  
   Analyse demand, competition, pricing, page value, reviews, purchase signals, and underserved combinations.

3. **Develop an original concept**  
   Generate new, age-appropriate and commercially differentiated book opportunities without copying existing products, characters, franchises, titles, covers, or visual identities.

4. **Produce a KDP-ready book package**  
   Create the interior, copyright page, ownership page, certificate of achievement, front cover, back cover, and full-wrap cover PDF with production validation.

---

## Key capabilities

### Amazon market research

- Searches Amazon US and Amazon UK using DataForSEO
- Returns public product signals such as:
  - search position
  - validated product title and ASIN
  - price
  - rating and review count
  - page count when available
  - price per page
  - Best Seller or Amazon’s Choice signals when available
  - Amazon’s publicly displayed “bought in past month” signal when available
- Builds marketplace-specific Amazon links
- Caches completed research to prevent accidental repeat API charges
- Separates verified market data from AI-generated analysis

### Demand and competition analysis

The app evaluates market evidence across several dimensions:

- **Demand signals:** recent purchase indicators, ratings, reviews, badges, and search visibility
- **Competition signals:** review strength, repeated concepts, dominant listings, and age-group saturation
- **Pricing signals:** average and median price, page-count range, and price-per-page value
- **Opportunity signals:** underserved age groups, subthemes, formats, activity types, and positioning gaps
- **Confidence:** reduced automatically when important data is missing

The app distinguishes between:

- **Popular bestsellers**, which demonstrate demand but may be difficult to compete with
- **Market opportunities**, where demand appears present but competition or differentiation may be more favourable

### AI niche opportunity analysis

The AI analysis answers six direct business questions:

1. Are customers buying this type of book?
2. What price do customers appear willing to pay?
3. How many pages do successful books commonly offer?
4. Is the niche dominated by established competitors?
5. Is there room for a differentiated original concept?
6. Should the publisher compete directly with the bestsellers or target a market gap?

Recommendations are presented as **original market opportunities**, not products to copy.

### Original concept generation

Each generated opportunity includes:

- original title
- target age group
- concept summary
- market-demand basis
- competition gap
- original differentiator
- suggested price range
- suggested page-count range
- confidence level

For anime-inspired projects, the app enforces non-infringement rules that reject protected franchises, named characters, logos, signature costumes, recognisable lookalikes, and “in the style of” prompts.

### Flexible book creation

The app supports two workflows:

#### Test Mode

- Fixed five-page sample
- Designed for prompt, concept, layout, and image-generation testing
- Not presented as an Amazon-ready publication

#### Amazon KDP Production Mode

- **Starter:** up to 15 main content pages
- **Adventure:** up to 30 main content pages
- **VIP:** more than 30 main content pages
- User-controlled colouring and activity-page distribution
- Automatic KDP publication-kit pages
- Dynamic support-page calculation to meet the required interior structure

### KDP production workflow

Production mode can prepare:

- copyright and disclaimer page
- “This Book Belongs To” page
- welcome or instructions page
- colouring and activity pages
- certificate of achievement
- final interior PDF
- full-colour front cover
- full-colour back cover
- full-wrap cover PDF
- KDP preflight checks
- production summary and AI-content disclosure reminder

---

## Product workflow

```text
Book Setup
    ↓
Amazon / Web Market Research
    ↓
Demand and Competition Analysis
    ↓
Five Original Market Opportunities
    ↓
Review and Edit Book Concept
    ↓
Generate and Validate Pages
    ↓
KDP Interior PDF + Full-Wrap Cover PDF
```

---

## Technology

| Area | Technology |
|---|---|
| Application platform | Google AI Studio full-stack application |
| Frontend | React and TypeScript |
| Backend | Node.js and Express |
| AI reasoning and concept generation | Google Gemini |
| Image generation | Gemini image generation |
| Amazon market data | DataForSEO Amazon Merchant API |
| Wider web research | Firecrawl |
| PDF generation | jsPDF |
| Testing | Automated Node/TypeScript test suite |

---

## Security and data integrity

The integration is designed so that external API credentials remain on the server.

- DataForSEO credentials are stored as server-side secrets
- API credentials are never returned to the browser
- Authentication headers are sanitised from logs and errors
- Amazon product facts must come from validated API results
- Gemini is not permitted to invent ASINs, prices, ratings, reviews, page counts, or purchase signals
- Missing information is displayed as unavailable rather than fabricated
- Paid research results are cached within the current project state

Expected environment variables include:

```env
DATAFORSEO_LOGIN=
DATAFORSEO_PASSWORD=
FIRECRAWL_API_KEY=
GEMINI_API_KEY=
```

Never commit real credentials, generated customer books, or private client data.

---

## Local development

The complete source application will be added to this repository after the current Google AI Studio build is exported and sanitised.

The intended local workflow is:

```bash
git clone https://github.com/aidemolab/ai-book-creator-market-research.git
cd ai-book-creator-market-research
npm install
cp .env.example .env
npm run dev
```

Run automated tests with:

```bash
npm test
```

Build the production application with:

```bash
npm run build
```

> These commands will be verified and updated once the exported application source is committed.

---

## Current development priorities

- Complete the high-demand, lower-competition opportunity model
- Validate all Amazon product links and structured field mappings
- Improve transparency around recommendation evidence and confidence
- Complete end-to-end KDP interior and full-wrap cover testing
- Add portfolio screenshots and an architecture diagram
- Export and sanitise the Google AI Studio source
- Add CI checks before making a public portfolio version

---

## Important limitations

- Amazon public data does not provide verified competitor unit sales
- Estimated daily purchases are calculated only when Amazon exposes a “bought in past month” signal
- Search position is not the same as sales rank
- Review count is not treated as sales
- Product page count and publication date may not be available for every listing
- Market-opportunity analysis supports business decisions but cannot guarantee commercial success
- AI-generated content must still be reviewed for quality, originality, suitability, and Amazon KDP compliance
- Direct automated publication to Amazon KDP is not currently part of this project

---

## Portfolio value

This project demonstrates the design and development of an end-to-end AI product that combines:

- product strategy
- business and market analysis
- external API integration
- secure server-side credential handling
- structured AI reasoning
- copyright-aware generative workflows
- state management and cost control
- deterministic document production
- automated validation and testing
- practical publishing requirements

It is designed as more than a content generator: it is a **decision-support and production platform for evidence-led independent publishing**.

---

## Roadmap

- [x] DataForSEO authentication and Amazon marketplace connection
- [x] Amazon US and UK research flows
- [x] Firecrawl web-trend research
- [x] Original anime-inspired safety policy
- [x] Flexible Test and KDP production modes
- [x] Market-result caching and API cost controls
- [x] Copyright, ownership, certificate, and cover requirements
- [ ] Finalise high-demand, lower-competition recommendation logic
- [ ] Complete live-data validation across multiple niches
- [ ] Export and commit the full application source
- [ ] Add screenshots and architecture documentation
- [ ] Complete KDP print-proof testing
- [ ] Prepare a sanitised public portfolio release

---

## Disclaimer

Amazon products and marketplace signals are used for research only. The platform does not recommend copying existing books, characters, titles, covers, franchises, or creative expression.

Generated opportunities are intended to help users develop new and differentiated concepts based on broad demand and competition patterns. The publisher remains responsible for copyright review, intellectual-property checks, content quality, Amazon KDP declarations, and final publication decisions.

---

## Repository status and licence

This repository is currently private and has no open-source licence. All rights are reserved unless a licence is added later.
