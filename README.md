# OG Image Skill

Generate social media preview images (Open Graph) and configure all meta tags for optimal sharing on Twitter/X, LinkedIn, Facebook, Slack, Discord, and more.

## Installation

### Via skills.sh (recommended)

```bash
npx skills add stevysmith/og-image-skill
```

### Via Claude Code plugin commands

```
/plugin marketplace add stevysmith/og-image-skill
/plugin install og-image@og-image-skill
```

After installation, the `/og-image` skill is available in Claude Code.

## What It Does

Creates a dedicated `/og-image` route in your project that renders a 1200x630 preview image matching your existing design system. Then screenshots it and configures all necessary meta tags.

**The skill automatically:**
- Explores your codebase to understand your design system (colors, fonts, components)
- Creates an OG image page using your existing aesthetic
- Screenshots at the correct 1200x630 dimensions
- Saves to your public folder
- Audits and adds missing meta tags (og:image, twitter:card, theme-color, etc.)

## Usage

```
/og-image
```

Run this command from within your web project directory. The skill will analyze your codebase and generate a contextually appropriate OG image.

## Prerequisites

Before using this skill, ensure you have:

1. **Playwright MCP Server** - Required for taking screenshots
   ```
   /install playwright@claude-plugins-official
   ```

2. **A web project** with a dev server running (Next.js, Vite, Astro, etc.)

3. **Dev server running** - Start your dev server before invoking the skill:
   ```bash
   npm run dev  # or yarn dev, pnpm dev, etc.
   ```

## Supported Frameworks

- Next.js (App Router & Pages Router)
- Vite + React
- Astro
- Remix
- Plain HTML/CSS

## What Gets Generated

1. **`/og-image` route** - A standalone page optimized for screenshots
2. **`/public/og-image.png`** - The 1200x630 screenshot
3. **Meta tag updates** - All necessary OG, Twitter, and misc meta tags

## Meta Tags Configured

- `og:image`, `og:image:width`, `og:image:height`, `og:image:alt`, `og:image:type`
- `twitter:card`, `twitter:image`, `twitter:title`, `twitter:description`
- `theme-color`, `msapplication-TileColor`
- Apple web app meta tags

## Cache Busting

After generating, use these tools to refresh social platform caches:
- Facebook/LinkedIn: https://developers.facebook.com/tools/debug/
- Twitter/X: https://cards-dev.twitter.com/validator
- LinkedIn: https://www.linkedin.com/post-inspector/

## Example Output

The skill generates an OG image that matches your project's design system:

- Uses your existing color palette and typography
- Includes your logo/branding
- Displays your product name and tagline
- Sized at exactly 1200x630 for optimal social previews

**See example templates in [`/examples`](./examples/):**

| File | Aesthetic | Style |
|------|-----------|-------|
| `sample-og-page.html` | Cosmic Luxury | Dark gradients, aurora colors, geometric orbs |
| `sample-og-minimal.html` | Editorial | Light, refined, magazine-inspired with abstract shapes |
| `sample-og-brutalist.html` | Neo-Brutalist | Bold typography, harsh colors, raw geometric blocks |
| `sample-og-ethereal.html` | Ethereal | Mesh gradients, glassmorphism, animated particles |

Open these HTML files in a browser to preview. The skill adapts its output to match your project's existing design language.

## Troubleshooting

**"Playwright not found"** - Install the Playwright MCP server first:
```
/install playwright@claude-plugins-official
```

**Screenshot is blank** - Make sure your dev server is running before invoking the skill.

**Meta tags not updating** - The skill modifies your layout file. Check that you have write access and no syntax errors were introduced.

## Learn More

- [skills.sh](https://skills.sh) - Discover more Claude Code skills
- [Open Graph Protocol](https://ogp.me/) - OG specification
- [Twitter Cards](https://developer.twitter.com/en/docs/twitter-for-websites/cards/overview/abouts-cards) - Twitter card documentation
