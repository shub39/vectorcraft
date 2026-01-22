# SVG to XML Converter Blueprint

## Purpose and Capabilities

This is a web-based tool that converts SVG (Scalable Vector Graphics) code into Android's Vector Drawable XML format. It allows users to paste their SVG code, customize properties like color, width, and height, and get the corresponding XML output for use in Android projects.

## Project Outline

### Design and Features (Version 1.0)

*   **Layout:** A two-column layout.
    *   The left column contains the input for the SVG code and customization options (color, width, height).
    *   The right column displays a live preview of the SVG and the generated XML output.
*   **Functionality:**
    *   **SVG Input:** A textarea for users to paste SVG code.
    *   **Customization:** Inputs for color, width, and height.
    *   **Live Preview:** The preview updates as the user modifies the SVG or customization options.
    *   **XML Output:** A read-only textarea displays the converted Vector Drawable XML.
    *   **Copy to Clipboard:** A button to copy the XML output.
*   **Styling:**
    *   A clean, modern interface with light and dark mode support.
    *   Uses CSS variables for theming.

### Current Task: Fix SVG to Vector Drawable Conversion

The current implementation has a critical flaw: it only processes the first `<path>` element found in the SVG. This causes issues with any SVG that uses multiple paths, groups (`<g>`), or other shapes (`<rect>`, `<circle>`, etc.), resulting in an incomplete or invisible icon in Android.

**Plan:**

1.  **Enhance SVG Parsing:** Modify the `convertSvgToXml` function in `src/pages/index.astro`.
2.  **Handle Multiple Elements:** The script will be updated to iterate through all elements within the SVG, not just the first path.
3.  **Support for Groups:** Add recursive processing for `<g>` (group) elements to handle nested shapes.
4.  **Convert Basic Shapes:** Implement conversion logic to transform basic SVG shapes (`<rect>`, `<circle>`, `<polygon>`, etc.) into the `<path>` data format that Android's Vector Drawable requires.
5.  **Generate Correct XML:** Construct the final XML with multiple `<path>` tags, preserving the structure and appearance of the original SVG.