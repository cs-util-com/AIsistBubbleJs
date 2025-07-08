# AIsistBubble

[![NPM Version](https://img.shields.io/npm/v/@csutil/support-bubble.svg)](https://www.npmjs.com/package/@csutil/support-bubble)

Lightweight support bubble that captures browser console logs and forwards user questions, bug reports, and feature requests to ChatGPT—pre‐filled with your repo context and intelligent prompts.

---

🔗 **Live Demo:**  
https://cs-util-com.github.io/AIsistBubbleJs/

---

## Features

- 📍 Fixed chat bubble in bottom-right corner (blue circle with white chat icon)  
- 💬 Small pop-over input for free-text questions, bug reports, or feature requests  
- 🐞 Captures all `console.log`, `console.warn`, `console.error`, and `console.info` messages  
- ✂️ Automatic truncation of logs to keep the URI-encoded query ≤ 8000 characters  
- 📄 Intelligently prompts ChatGPT with the current page's URL for context.
- 📧 Customizable bug report email address.
- 🔗 Opens ChatGPT in a new tab with `https://chat.openai.com/?q=<encoded prompt>`  
- 🚫 No backend, cookies, or localStorage—100% client-side  
- 🎨 Dark mode support

---

## Installation

1.  **Install via npm:**
    ```bash
    npm install @csutil/support-bubble
    ```
    Then, include the script in your HTML:
    ```html
    <script src="node_modules/@csutil/support-bubble/support-bubble.js"></script>
    ```

2.  **Or, use a CDN:**
    ```html
    <script src="https://cdn.jsdelivr.net/npm/@csutil/support-bubble/support-bubble.js"></script>
    ```

3.  **Or, download manually:**
    - Download `support-bubble.js` from this repository.
    - Copy it to your project and include it with a script tag:
    ```html
    <script src="support-bubble.js"></script>
    ```

---

## Usage

1. **Click** the blue support bubble in the bottom-right corner.
2. **Type** your question, bug report, or feature request into the pop-over textarea.
3. **Click** **Submit** (or press Ctrl/⌘ + Enter).
4. A new tab opens with ChatGPT, pre-filled with:

   * A rules-based prompt for Q&A or bug reports
   * Your text
   * Captured console log (truncated if needed)
   * The current URL

5. **Edit** or **submit** directly in ChatGPT.

---

## Configuration

You can configure the support bubble by setting a global JavaScript variable **before** including the `support-bubble.js` script.

- `window.BUG_REPORT_EMAIL`: The email address where users should send bug reports. If not set, the prompt will ask ChatGPT to find a suitable support email.

Example:
```html
<script>
  window.BUG_REPORT_EMAIL = "support@example.com";
</script>
<script src="support-bubble.js"></script>
```

---

## Customization

You can customize the support bubble by modifying the `support-bubble.js` file:

*   **Position & Style:** Modify the CSS rules at the top of the file.
*   **Log Capture:** Modify the `captureConsole` function to change which console methods are captured.
*   **Prompt Engineering:** Adjust the `buildPrefix` function to change the instructions given to ChatGPT.
*   **UI Text:** Change the HTML strings (`bubbleHTML`, `popoverHTML`) to alter the UI text and elements.

---

## License
See [LICENSE](./LICENSE)