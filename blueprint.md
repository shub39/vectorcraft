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

### Current Task: Handle SVG `viewBox` Offset

The current conversion logic does not handle SVGs where the `viewBox` attribute has a non-zero `x` or `y` offset (e.g., `viewBox="-10 -10 100 100"`). This results in an incorrect Vector Drawable where the icon is rendered off-canvas and is therefore invisible.

**Plan:**

1.  **Parse Full `viewBox`:** Modify the `convertSvgToXml` function in `src/pages/index.astro` to parse all four values (`x`, `y`, `width`, `height`) from the `viewBox` attribute.
2.  **Apply Translation:** If the `x` or `y` offset values are not zero, wrap the generated `<path>` elements in a `<group>` tag.
3.  **Set Group Transforms:** Add `android:translateX` and `android:translateY` attributes to the `<group>`. The values will be the *negative* of the `viewBox`'s `x` and `y` values, respectively. This will shift the drawing canvas to match the original SVG's coordinate system, making the icon visible.
