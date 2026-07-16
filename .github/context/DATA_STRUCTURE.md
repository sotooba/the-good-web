# Data Structure Spec: `websites.json`

## 1. Schema Definitions
The database file maps an array of category blocks. Each block carries meta coordinates for rendering navigation anchors and holds a sub-array of individual website assets. 

Individual site schemas contain basic name, navigation parameters, short informational descriptions, an icon key identifier, and a mandatory boolean tracking configuration indicating mandatory user creation rules.

## 2. Model Structure
The local JSON data repository (`src/_data/websites.json`) must track exactly this validation architecture:

```json
[
  {
    "category_name": "Media Utilities",
    "category_slug": "media",
    "sites": [
      {
        "name": "OpenCut",
        "url": "https://example.com",
        "desc": "A deeply versatile browser-based multi-track video timeline tool.",
        "icon": "film",
        "requires_signup": false
      },
      {
        "name": "CapCut Web",
        "url": "https://capcut.com",
        "desc": "A fast browser timeline for editing videos and cutting quick social media clips.",
        "icon": "video",
        "requires_signup": true
      }
    ]
  },
  {
    "category_name": "Design & Productivity",
    "category_slug": "design",
    "sites": [
      {
        "name": "Excalidraw",
        "url": "https://excalidraw.com",
        "desc": "A polished collaborative whiteboard framework for diagrams and quick sketches.",
        "icon": "palette",
        "requires_signup": false
      }
    ]
  }
]
```

## 3. Template Generation Rules for Eleventy
* **Grid Layout Implementation**: The outer layout loop generates the category header blocks. Underneath each category title, render a wrapper div using the explicit Bootstrap card grid classes (`class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4"`).
* **Component Allocation**: The internal engine steps through the nested `sites` nodes to output an individual grid column wrapper containing the structured card layout component.
* **Icon Rendering**: Use the string from the `icon` property to conditionally embed or toggle corresponding free vector graphics (such as an inline SVG or a Bootstrap Icon font class indicator).
* **Indicator Logic**: Evaluate `requires_signup`. If `true`, output the clean, custom theme-compliant signup text indicator pill badge inside the card footer. If `false`, emit no badge markup.
