# OG Image Skill

Generate social media preview images (Open Graph) and configure all meta tags for optimal sharing on Twitter/X, LinkedIn, Facebook, Slack, Discord, and more.

## Installation

1. Add the marketplace:
```
/plugin marketplace add stevysmith/og-image-skill
```

2. Install the plugin:
```
/plugin install og-image@og-image-skill
```

That's it. The `/og-image` skill is now available.

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
