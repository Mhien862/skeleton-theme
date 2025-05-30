<h1 align="center" style="position: relative;">
  <br>
  ✈️ Airport Theme
  <br>
</h1>

A modern, professional Shopify theme inspired by airport and travel aesthetics. Clean design with smooth user experience, perfect for travel, fashion, electronics, and lifestyle brands.

<p align="center">
  <a href="./LICENSE.md"><img src="https://img.shields.io/badge/License-MIT-green.svg" alt="License"></a>
</p>

## ✨ Features

- **Modern Airport-Inspired Design**: Clean, minimalist layout with aviation aesthetics
- **Responsive Design**: Optimized for all devices and screen sizes  
- **Fast Performance**: Lightweight code with optimized loading times
- **Customizable**: Easy-to-use theme customizer with lots of options
- **SEO Optimized**: Built with SEO best practices
- **Accessibility**: WCAG compliant and screen reader friendly

## 🚀 Getting started

### Prerequisites

Before starting, ensure you have the latest Shopify CLI installed:

- [Shopify CLI](https://shopify.dev/docs/api/shopify-cli) – helps you download, upload, preview themes, and streamline your workflows

If you use VS Code:

- [Shopify Liquid VS Code Extension](https://shopify.dev/docs/storefronts/themes/tools/shopify-liquid-vscode) – provides syntax highlighting, linting, inline documentation, and auto-completion specifically designed for Liquid templates

### Preview

Preview this theme using Shopify CLI:

```bash
shopify theme dev
```

## 🎨 Theme Features

### Design Elements
- **Clean Typography**: Modern font stack optimized for readability
- **Smooth Animations**: Subtle micro-interactions for better UX
- **Color Palette**: Professional blue and gray tones inspired by aviation
- **Grid System**: Flexible layout system for different content types

### Sections Included
- **Hero Banner**: Eye-catching homepage banner with CTA
- **Featured Products**: Showcase your best products
- **Collections Grid**: Display product categories beautifully
- **Testimonials**: Customer reviews and social proof
- **Newsletter**: Email signup with modern styling
- **Footer**: Comprehensive footer with links and info

## 📁 Theme architecture

```bash
.
├── assets          # CSS, JS, images, icons, fonts
├── blocks          # Reusable UI components
├── config          # Theme settings and configuration
├── layout          # Page layout templates
├── locales         # Translation files
├── sections        # Main content sections
├── snippets        # Reusable code fragments
└── templates       # Page templates
```

To learn more, refer to the [theme architecture documentation](https://shopify.dev/docs/storefronts/themes/architecture).

### Templates

[Templates](https://shopify.dev/docs/storefronts/themes/architecture/templates#template-types) control what's rendered on each type of page in a theme.

The Skeleton Theme scaffolds [JSON templates](https://shopify.dev/docs/storefronts/themes/architecture/templates/json-templates) to make it easy for merchants to customize their store.

None of the template types are required, and not all of them are included in the Skeleton Theme. Refer to the [template types reference](https://shopify.dev/docs/storefronts/themes/architecture/templates#template-types) for a full list.

### Sections

[Sections](https://shopify.dev/docs/storefronts/themes/architecture/sections) are Liquid files that allow you to create reusable modules of content that can be customized by merchants. They can also include blocks which allow merchants to add, remove, and reorder content within a section.

Sections are made customizable by including a `{% schema %}` in the body. For more information, refer to the [section schema documentation](https://shopify.dev/docs/storefronts/themes/architecture/sections/section-schema).

### Blocks

[Blocks](https://shopify.dev/docs/storefronts/themes/architecture/blocks) let developers create flexible layouts by breaking down sections into smaller, reusable pieces of Liquid. Each block has its own set of settings, and can be added, removed, and reordered within a section.

Blocks are made customizable by including a `{% schema %}` in the body. For more information, refer to the [block schema documentation](https://shopify.dev/docs/storefronts/themes/architecture/blocks/theme-blocks/schema).

## Schemas

When developing components defined by schema settings, we recommend these guidelines to simplify your code:

- **Single property settings**: For settings that correspond to a single CSS property, use CSS variables:

  ```liquid
  <div class="collection" style="--gap: {{ block.settings.gap }}px">
    ...
  </div>

  {% stylesheet %}
    .collection {
      gap: var(--gap);
    }
  {% endstylesheet %}

  {% schema %}
  {
    "settings": [{
      "type": "range",
      "label": "gap",
      "id": "gap",
      "min": 0,
      "max": 100,
      "unit": "px",
      "default": 0,
    }]
  }
  {% endschema %}
  ```

- **Multiple property settings**: For settings that control multiple CSS properties, use CSS classes:

  ```liquid
  <div class="collection {{ block.settings.layout }}">
    ...
  </div>

  {% stylesheet %}
    .collection--full-width {
      /* multiple styles */
    }
    .collection--narrow {
      /* multiple styles */
    }
  {% endstylesheet %}

  {% schema %}
  {
    "settings": [{
      "type": "select",
      "id": "layout",
      "label": "layout",
      "values": [
        { "value": "collection--full-width", "label": "t:options.full" },
        { "value": "collection--narrow", "label": "t:options.narrow" }
      ]
    }]
  }
  {% endschema %}
  ```

## CSS & JavaScript

For CSS and JavaScript, we recommend using the [`{% stylesheet %}`](https://shopify.dev/docs/api/liquid/tags#stylesheet) and [`{% javascript %}`](https://shopify.dev/docs/api/liquid/tags/javascript) tags. They can be included multiple times, but the code will only appear once.

### `critical.css`

The Skeleton Theme explicitly separates essential CSS necessary for every page into a dedicated `critical.css` file.

## Contributing

We're excited for your contributions to the Skeleton Theme! This repository aims to remain as lean, lightweight, and fundamental as possible, and we kindly ask your contributions to align with this intention.

Visit our [CONTRIBUTING.md](./CONTRIBUTING.md) for a detailed overview of our process, guidelines, and recommendations.

## License

Skeleton Theme is open-sourced under the [MIT](./LICENSE.md) License.
