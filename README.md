# Clear-Lens - News Bias Detector

## Project Overview
ClearLens is a high-fidelity media literacy tool built for **Next Byte Hacks V2**. It empowers readers to "see past the spin" by identifying political framing, loaded language, and missing perspectives in news articles through real-time URL analysis.

## Core Features
- **AI-Powered Analysis:** Leverages **Gemini 2.0 Flash** to perform deep linguistic and sentiment audits.
- **Interactive Bias Spectrum:** A high-impact visual scale that animates to show an article's political lean from "Progressive" to "Conservative."
- **Live Rhetoric Scanning:** A typewriter hero demo that simulates real-time analysis by highlighting loaded terms.
- **Global Insight Engine:** A custom SVG-rendered visualization showing rhetoric distribution over the last 24 hours.
- **Complete User Flow:** Includes a searchable **Analysis Archive**, detailed **Methodology** breakdown, and a full **Authentication Suite** (Sign In/Sign Up) for saving custom reports.
- **Editorial Archive:** A filterable repository of past media evaluations with instant-glance bias indicators.

## Technical Implementation
ClearLens is built as a lightweight, high-fidelity application using **Vanilla HTML, CSS, and JavaScript**, with **Tailwind CSS** for its precise editorial design system.

### Integration with Gemini API
The app handles structured system prompts to ensure the AI returns precise JSON data for:
- Political lean & bias positioning
- Loaded phrases with contextual explanations
- Missing perspectives and framing strategies
- Source credibility scores

### Local Setup
1. Clone this repository.
2. Open `index.html` in any modern web browser.
3. Obtain a Gemini API key from [Google AI Studio](https://aistudio.google.com/).
4. Enter your key in the collapsible configuration field below the navigation bar.

## Design System
- **Typography:** Work Sans (Headlines), Inter (Body).
- **Palette:** Navy (#091426), Amber Accent (#fe932c), and Neutral Greys.
- **Aesthetic:** "Precision Instrument" — flat, editorial, and high-contrast.

## Project Status
Developed for Next Byte Hacks V2.
**Deadline:** May 31, 2026.
