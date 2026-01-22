# SVG to XML Vector Drawable Converter

## Purpose and Capabilities

This web application provides a user-friendly interface for converting SVG code into Android's XML Vector Drawable format. It allows for customization of the icon's color and size, offers a real-time preview, and includes a "Copy to Clipboard" feature for the generated XML. The application is designed with Material 3 aesthetics, uses the Google Sans font, and supports both light and dark themes.

## Project Outline

### Style and Design

*   **Framework:** Astro.js
*   **Design Language:** Material 3
*   **Font:** Google Sans
*   **Themes:** Light and Dark mode support.
*   **Layout:** A single-page application with a two-column layout. The left column will contain the input fields for the SVG code and customization options, while the right column will display the icon preview and the generated XML output.

### Features

*   **SVG Input:** A text area for users to paste their SVG code.
*   **Color Customization:** A color picker to change the icon's fill color.
*   **Size Customization:** Input fields to adjust the width and height of the icon.
*   **Live Preview:** A real-time preview of the icon that updates as the user modifies the SVG code or customization options.
*   **XML Output:** A read-only text area displaying the generated XML Vector Drawable code.
*   **Copy to Clipboard:** A button to copy the generated XML to the clipboard.
*   **Responsive Design:** The layout will adapt to different screen sizes.

## Current Task: Initial Setup

*   **`blueprint.md`:** Create the blueprint file.
*   **Cleanup:** Remove un-used files from the default astro project.
*   **Layout:** Update the main layout with Google Sans font and theme colors.
*   **Index Page:** Create the main page with the UI structure.
*   **Functionality:** Add the client-side script for the conversion logic.
*   **Styling:** Apply Material 3 styling to the UI elements.
