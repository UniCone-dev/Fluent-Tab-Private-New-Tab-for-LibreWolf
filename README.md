# Fluent-Tab-Private-New-Tab-for-LibreWolf
Windows 11 Start-Menu-style new tab page. 100% local, open-source, no tracking, no analytics, no accounts. Everything is saved directly inside your browser's local storage.

# Key Features

    OS-style taskbar (bottom of screen, always visible): The Start button and pinned apps are now always aligned to the center of the taskbar (just like Windows 11) — pin any AI/folder app using the "+" button or create a new custom app. The right tray displays a weather icon next to the temperature and clock, alongside a language switcher.

    3 languages, fully translated: English (formal, default), Русский (Russian), Français (French). Every settings tab, button, hint, and placeholder is fully translated (excluding the search bar). Switch languages instantly via the top-right globe icon 🌐 or via Settings → Layout — clock and date formats automatically update to match the selected language.

    Custom app icons: Instead of just letters or emojis, you can upload your own image for any app (AI, folder, taskbar) via the "Custom icon image" option when editing an app.

    Fully customizable panel size: Adjust width, max-height, scale, and corner roundness with live previews, just like the search bar (Settings → Layout).

    Profile: Set your name and display picture (saved locally on your device). Optionally, you can connect your Google account by providing your own Google OAuth Client ID (Settings → Profile). Since this extension does not use any shared or centralized authentication server, Google login will only function after you enter your Client ID (instructions provided below).

    Search bar (top): Entering a link/URL opens it directly; entering regular text initiates a privacy-focused web search (default: DuckDuckGo — can be changed to Startpage, Brave, Google, or Bing).
AI row: Claude, Gemini, and ChatGPT are pinned by default. Use the "+" button to add any local LLM UI (llama.cpp / Ollama / KoboldAI / text-gen-webui, or any custom http://localhost:PORT) — zero external network calls; everything runs locally on your machine.

Folders: Default folders include Google, Customize, Movies & Series, Private Chat, Music, and Other — all are fully editable (rename, delete, or add links/apps as needed).

Weather + live clock (bottom-right): Search for any city worldwide or use the "current location" button. Network requests are made only when you explicitly set your location (powered by Open-Meteo — free, no API key, no tracking). The clock automatically syncs to the timezone of the selected location.

Settings (gear icon, top-right):

    Appearance: Light/dark/auto theme options, accent color selection, customizable backgrounds (upload custom images or select gradient presets), background blur, glass opacity, and toggleable animations.

    Layout: Panel placement options (center/top/bottom/left/right), account name customization, and clock format settings.

    Apps & Folders: Manage all folders and app links.

    AI: Configure local LLM presets.

    Privacy: Select search engine, export/import configuration settings as JSON, or perform a full system reset.

    Advanced CSS: Apply custom CSS rules directly for full theming control.


# Signing in with a Google Account (Optional)

Navigate to "APIs & Services" → "Credentials" → "Create OAuth client ID" → select Chrome App / Web application as the application type.

    After loading the extension, check your extension ID in about:debugging or about:addons. Add https://<extension-id>.extensions.allizom.org/ as an Authorized Redirect URI (the browser will display this URL in the console or error log if a mismatch occurs).

    Copy your Client ID, paste it into Settings → Profile, and click "Connect Google Account".

Because this connects directly to your personal Google Cloud project without involving any third-party or developer servers, completing these manual setup steps is required.

# Privacy

The extension requests only storage permissions (for saving settings locally) and geolocation permissions (triggered strictly when you press the "current location" button). It contains no analytics, telemetry, or tracking scripts. The complete codebase consists solely of four readable files:
manifest.json, newtab.html, css/style.css, and js/script.js.


# How to Install in LibreWolf

Option A — Temporary Load (Easiest for testing)

    Open about:debugging#/runtime/this-firefox in LibreWolf.

    Click "Load Temporary Add-on…".

    Select the manifest.json file inside the project directory.

    Open a new tab — your new tab page will update instantly.
    ⚠️ Note: This temporary installation will revert whenever the browser restarts, requiring you to reload the file.


Option B — Permanent Installation (Disabling signing requirements)

    Open about:config in LibreWolf.

    Search for xpinstall.signatures.required and set it to false (LibreWolf officially supports this toggle due to its privacy-focused design).

    Package the project folder into an .xpi file (a standard ZIP archive renamed to .xpi). Then navigate to about:addons → click the gear icon → select "Install Add-on From File".


# Customization & Setting Icons

    Right-click any app tile to edit or delete it.

    Click the "+" or "Manage" buttons within a section to add new applications.

    Default app icons utilize letters or emojis to prevent remote image fetching, maintaining fast performance and high privacy. You can also upload custom local image icons for any app without making requests to third-party servers.


# Open Source License

Built without build steps, bundlers, or external dependencies — structured purely with standard HTML, CSS, and JavaScript. Free to copy, modify, and redistribute under the MIT License (refer to the LICENSE file for details).


Credits

    Design & Project Lead — UniCone-dev

    Coding Assistance — Claude (Anthropic)




