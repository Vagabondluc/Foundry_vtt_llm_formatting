![Foundry VTT Screenshot](https://raw.githubusercontent.com/Vagabondluc/Foundry_vtt_llm_formatting/refs/heads/main/2025-05-22%2005_01_29-Foundry%20Virtual%20Tabletop.jpg)

# Foundry_vtt_llm_formatting
Formatting guide for Foundry Vtt using LLM, this is a compendium module for foundry. 

The specific URL for the module.json file of the "Foundry_vtt_llm_formatting" compendium module is:
```
[https://raw.githubusercontent.com/Vagabondluc/Foundry_vtt_llm_formatting/refs/heads/main/modules/journal-formatting-system-for-large-language-models/module.json](https://github.com/Vagabondluc/Foundry_vtt_llm_formatting/releases/download/v1.0.0/module.json)
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
