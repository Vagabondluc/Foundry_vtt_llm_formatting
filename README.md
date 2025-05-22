![Foundry VTT Screenshot](https://raw.githubusercontent.com/Vagabondluc/Foundry_vtt_llm_formatting/refs/heads/main/2025-05-22%2005_01_29-Foundry%20Virtual%20Tabletop.jpg)

# Foundry_vtt_llm_formatting
Formatting guide for Foundry Vtt using LLM, this is a compendium module for foundry. 

The specific URL for the module.json file of the "Foundry_vtt_llm_formatting" compendium module is:
```
https://raw.githubusercontent.com/Vagabondluc/Foundry_vtt_llm_formatting/refs/heads/main/modules/journal-formatting-system-for-large-language-models/module.json
```
## Empowering Foundry VTT Journal Styling with Large Language Models

This guide outlines a workflow for utilizing Large Language Models (LLMs) to automatically generate professionally styled journal entries within Foundry Virtual Tabletop. By providing the LLM with a specialized knowledge base, users can transform raw text into visually engaging content without needing technical HTML or CSS expertise.

### 1. Establishing the LLM's Knowledge Base

To enable the LLM to perform advanced journal styling, it must first be "trained" or provided with the foundational and advanced styling guidelines. This is achieved by feeding the LLM the complete HTML content of the following three documentation files:

- **`Advanced Prompt`**: This file acts as the primary directive for the LLM, outlining its mission to transform content into visually stunning, professionally formatted entries without requiring user decisions. It details the editor's capabilities and limitations, including supported CSS features and security-blocked elements, and establishes a system for intelligent content analysis, theme detection, and automatic styling application with strict readability and contrast standards.
- **`Simple Prompt`**: This guide provides the LLM with a baseline of simple, universally safe styling practices, covering basic HTML structure, essential font families, inline formatting, lists, and simple styling elements.
- **`Intermediate Prompt`**: This document equips the LLM with knowledge of more advanced styling techniques, including CSS Grid and Flexbox layouts, an expanded font library, advanced visual effects (gradients, shadows, filters), and professional layout patterns.

To provide this knowledge base:

Copy the entire Text content of the file you will use, clearly demarcating the start and end of the document. For instance:

```
**START Of Advanced Prompt***
... (full content of Advanced Prompt) ...
***END Of Advanced Prompt***

((
Content You want to format
))
```

### 2. Initiating a Journal Styling Request

Once the LLM has processed the styling guides, you can provide your raw journal content for formatting.

**Your prompt should explicitly include:**

- **A Clear Directive:** Instruct the LLM to format the provided text as a Foundry VTT journal entry.
- **The Raw Journal Content:** Embed the text you wish to be styled directly within the prompt.
- **Emphasis on Autonomous Styling:** Reiterate the LLM's core mission to "Automatically transform any journal content into visually stunning, professionally formatted entries that maximize Foundry VTT's WYSIWYG editor capabilities without requiring user decisions or technical knowledge" and to "Never ask users for formatting choices". This ensures the LLM generates a complete, styled output without seeking further input from you.

**Example Prompt:**

"Using the Foundry VTT journal styling system you were provided, please transform the following raw text into a Foundry VTT journal entry. Do NOT ask any questions about styling choices; make intelligent decisions based on the provided guides. Deliver a professional-grade, visually stunning result.

**RAW JOURNAL CONTENT START:**

The ancient tome lay open on the dusty pedestal. Its pages, brittle with age, whispered tales of forgotten gods and a time before empires. A faded illustration depicted a towering, skeletal dragon soaring over a desolate wasteland. Nearby, a small note from the local historian, Elara, mentioned rumors of a hidden chamber beneath the ruins, guarded by spectral guardians. She also included a table of known artifacts recovered from similar sites.

Artifacts from the Ruins

Name | Description | Value

Orb of Shifting Sands | Pulsates with faint light, controls minor earth magic | 500 GP

Broken Amulet of Protection | A fragment, offers negligible defense | 10 GP

Scroll of Whispers | Contains ancient curses, untranslated | Undetermined

**RAW JOURNAL CONTENT END**"

### 3. Guiding Subsequent Interactions and Refinements

While the aim is a perfect initial output, minor adjustments may occasionally be desired. Guide the LLM by focusing on the desired aesthetic outcome rather than attempting to dictate specific CSS properties.

- **Be Specific About Effects:** Instead of requesting "change `background-color` to `blue`," describe the visual goal, e.g., "Make the background of this section more thematic for a 'Mystical/Arcane' setting."
- **Leverage Detected Themes:** If the initial styling doesn't quite capture the intended mood, prompt the LLM to re-style it with a specific theme in mind. For example, "Can you re-style the 'Whispering Woods' entry to emphasize a more *dark fantasy/ominous* feel, using the appropriate theme colors and fonts from your knowledge base?".
- **Suggest Specific Templates:** If the LLM didn't automatically identify a content type, you can suggest it: "For this character description, please apply the 'Character/NPC Auto-Template'.".
- **Address Readability Issues (Critical):** If the text is difficult to read due to poor color contrast, explicitly state the problem. For example, "The text in the 'Magic Spell' section is difficult to read. Please ensure it adheres to the 'Minimum 4.5:1 contrast ratio for all text' rule.". The LLM is instructed to prioritize readability and accessibility above all visual effects.
- **Understand Blocked Features:** If the LLM explains that a requested feature is unsupported (e.g., interactive buttons), acknowledge its explanation and rephrase your request using supported alternatives. The LLM is aware that form elements, JavaScript, and event handlers are completely stripped.

### 4. Integrating with Foundry VTT

Once you receive the LLM's styled HTML output:

1. **Copy the entire HTML code** provided by the LLM.
2. In Foundry VTT, open your desired journal entry.
3. Locate and click the `Source Code` or `&lt;&gt;` button within the WYSIWYG editor to switch to the HTML source view.
4. **Paste the copied HTML code** into the source editor.
5. Save the journal entry.

By adhering to these instructions, you empower the LLM to act as a sophisticated design assistant, allowing you to create visually impressive Foundry VTT journal entries with minimal manual effort and no prior technical knowledge.

## Foundry VTT Journal Styling Approaches: A Comprehensive Guide

This document outlines three distinct methods for styling journal entries within Foundry Virtual Tabletop, ranging from basic formatting to advanced, automated solutions. These methods are designed to cater to different levels of user technical expertise and desired visual complexity.

### 1. Simple Journal Styling Method

This approach focuses on creating clear and readable journal entries with minimal complexity. It emphasizes fundamental HTML elements and straightforward styling.

**Key Features:**

- **Basic HTML Structure:** Utilizes standard headers (h1-h6), paragraph tags (`<p>`), blockquotes (`<blockquote>`), and preformatted text (`<pre><code>`).
- **Text Alignment:** Employs basic CSS classes like `align-left`, `align-center`, `align-right`, and `align-justify` for text positioning.
- **Essential Font Families:** Recommends reliable fonts such as 'Arial', 'Times New Roman', and 'Courier New' for core text, alongside 'IM Fell English', 'Bookinsanity', and 'UnifrakturCook' for fantasy themes, and 'Black Ops One', 'Jim Nightshade', and 'Montserrat' for display purposes.
- **Inline Formatting:** Supports standard HTML tags for bold (`<strong>`), italic (`<em>`), inline code (`<code>`), and basic inline CSS for underlined and strikethrough text, as well as superscript and subscript.
- **Lists:** Includes both bulleted (`<ul>`) and numbered (`<ol>`) lists, with support for nesting.
- **Basic Elements:** Incorporates horizontal rules (`<hr>`), hyperlinks (`<a>`), and images (`<img>`) with simple resizing, and basic table structures (`<table>`).
- **Simple Color Coding:** Allows for direct application of colors using inline styles for thematic emphasis (e.g., red for danger, green for success, blue for magic, gold for treasure).

### 2. Intermediate Journal Styling Method

Building upon the simple method, this approach enables the creation of visually richer and more professionally formatted journals by incorporating advanced CSS features.

**Key Features:**

- **Advanced Layout Systems:** Introduces CSS Grid (`display: grid`, `grid-template-columns`, `gap`) and Flexbox (`display: flex`, `justify-content`, `align-items`, `flex-wrap`, `flex-grow`) for complex content arrangement.
- **Expanded Font Library:** Provides access to a comprehensive list of 29 font families, categorized by style (serif, sans-serif, fantasy/gaming, display/decorative, monospace, and decorative), offering a broader range of thematic choices.
- **Advanced Visual Effects:** Supports all CSS color formats (HEX, RGB, RGBA, HSL, HSLA, named colors), advanced linear and radial gradients, sophisticated box and text shadows, and various CSS filters (blur, brightness, contrast, opacity).
- **Transforms:** Allows for static CSS transforms like `rotate()`, `scale()`, `skew()`, and `translate()` for visual adjustments.
- **Professional Layout Patterns:** Demonstrates the implementation of card-based layouts, detailed headers with advanced styling, and responsive tables for improved data presentation.

### 3. Advanced Journal Styling Method for LLMs

This method leverages the power of Large Language Models (LLMs) to automatically transform raw journal content into stunning, professionally designed entries without requiring manual styling or user decisions. It is based on a comprehensive understanding of Foundry VTT's WYSIWYG editor capabilities and limitations.

**Core Principles for LLM Implementation:**

- **Automatic Content Analysis:** The LLM parses content to detect type (e.g., character, location, lore, combat, quest), structure, emotional tone, and thematic indicators.
- **Automated Theme Selection:** Based on content analysis, the LLM intelligently selects appropriate color palettes, font combinations, and visual effects (e.g., Fantasy Medieval, Dark Fantasy/Horror, Urban/Modern, Wilderness/Nature, Mystical/Arcane themes).
- **Strategic Layout Architecture:** Applies optimal container systems (single column, CSS Grid, Flexbox) and creates a visual flow that guides reader attention, ensuring responsive design principles.
- **Advanced Styling Application:** Automatically implements sophisticated typography, theme-appropriate color psychology, and strategic visual effects (gradients, shadows, transforms).
- **Mandatory Readability and Accessibility:** Strictly adheres to critical readability rules, including a minimum 4.5:1 contrast ratio for all text, optimal line length, appropriate line height, and sufficient white space.
- **Foundry VTT Optimization:** Ensures max-width containers, scalable font sizing, and mobile-friendly layouts, while avoiding overly complex CSS that could impact performance.
- **Security Restrictions (Crucial):** The LLM is explicitly instructed to **never** use JavaScript, event handlers, form elements, SVG graphics, or HTML5 Canvas, as these are security-blocked by the Foundry VTT editor.
- **"Never Ask Users" Directive:** The system is designed to make all styling decisions automatically, eliminating the need for user input on formatting choices.
- **"Always Deliver Professional-Grade" Output:** The ultimate goal is to produce visually stunning, immersive, and perfectly readable journal entries that appear to be designed by an expert.

This method serves as a directive for LLMs, enabling them to produce high-quality Foundry VTT journal entries with minimal user interaction.
