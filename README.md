# AI Subtitle Translator

Welcome to **AI Subtitle Translator** – an advanced, web-based tool that leverages artificial intelligence to translate subtitle files quickly and accurately. Built with [React](https://react.dev/) and [Vite](https://vitejs.dev/), this project aims to make multilingual video accessibility easy for everyone.

-----

## 🚀 Demo

*You can try out the live demo here:*

> **[Demo URL – Coming Soon\!]**

*(This section can be updated with your live deployment URL.)*

-----

## ✨ Features

  - **Multiple Format Support:** Translate `.srt`, `.vtt`, `.ass`, and `.ssa` files.
  - **Intelligent Parsing:** Preserves all original timestamps, styles, and formatting by only translating the dialogue text.
  - **Secure API Key Handling:** Your OpenRouter API key is stored exclusively in your browser's local storage and is never sent to any server other than OpenRouter's.
  - **Advanced Error Handling:**
      - **Review Panel:** Automatically detects lines the AI missed and presents them for a targeted re-translation of only the failed lines.
      - **Safety Net:** Ensures no lines are ever lost by filling in missed translations with the original text.
  - **Dynamic Customization:**
      - **Custom Models & Languages:** Add and save your own AI models and target languages through the settings panel.
      - **Custom .ass/.ssa Title:** Dynamically set the `Title:` field for `.ass` and `.ssa` files directly from the UI.
  - **Modern UI:** A clean, responsive, and animated interface built with Tailwind CSS.
  - **Easy Configuration:** A single `config` object at the top of `App.jsx` allows for easy branding and default setting changes.

-----

## 🖥️ Self-Host & Installation

Want to run AI Subtitle Translator on your own server? Follow these simple steps to set it up locally. You will need [Node.js](https://nodejs.org/) installed.

1.  **Clone the Repository**

    ```bash
    git clone [https://github.com/your-username/your-repo.git](https://github.com/your-username/your-repo.git)
    cd your-repo
    ```

2.  **Install Dependencies**

    ```bash
    npm install
    ```

3.  **Configure Tailwind CSS**

    ```bash
    npm install -D tailwindcss@^3.0 postcss autoprefixer
    npx tailwindcss init -p
    ```

    *(Ensure your `tailwind.config.js` and `src/index.css` are configured as per the Vite guide.)*

4.  **Start the Development Server**

    ```bash
    npm run dev
    ```

    The app will now be running locally at `http://localhost:5173/`.

5.  **Build for Production**

    ```bash
    npm run build
    ```

    This creates a `dist` folder with your production-ready files, which you can deploy to any static hosting service.

-----

## 📝 How it Works

AI Subtitle Translator makes the translation process seamless:

1.  **Configure:** The user enters their private OpenRouter API key.
2.  **Upload:** A subtitle file (`.srt`, `.vtt`, `.ass`, or `.ssa`) is uploaded.
3.  **Parse:** The application intelligently reads the file, extracting *only* the dialogue that needs translation while safely storing all timestamps and style codes.
4.  **Translate:** The dialogue text is sent to the selected AI model.
5.  **Rebuild:** The application meticulously reconstructs the original file, inserting the translated text back into its correct place, ensuring no formatting is lost.
6.  **Review & Download:** The user can review the translated text, re-translate any lines the AI missed, and download the final, perfectly formatted file.

-----

## 🔧 Customization

Customizing the application with your own branding and defaults is simple. Open the `src/App.jsx` file and edit the `config` object at the very top:

```javascript
const config = {
    // 1. Your GitHub repository URL
    githubRepoUrl: "[https://github.com/your-username/your-repo](https://github.com/your-username/your-repo)",

    // 2. Your GitHub ribbon image. Place the image in the `public` folder.
    githubRibbonImage: "/github-ribbon.png",

    // 3. The text that appears in the footer
    footerText: "© 2025 Your Company Name. All Rights Reserved.",

    // 4. Default AI model and language when the app loads
    defaultModel: 'anthropic/claude-3-haiku',
    defaultLanguage: 'Spanish',

    // 5. Default title for new .ass/.ssa subtitle files
    defaultAssTitleTemplate: "Translated by AI to ${language}"
};
```

📂 Project Structure

.
├── public/
│   └── github-ribbon.png  // Your static assets go here
├── src/
│   ├── App.jsx            // Main application component and logic
│   ├── index.css          // Tailwind CSS directives
│   └── main.jsx           // React entry point
├── .gitignore
├── index.html
├── package.json
├── postcss.config.js
├── tailwind.config.js
├── vite.config.js
└── README.md

🤝 Contributing

Contributions are welcome! Please feel free to open an issue to report a bug or suggest a feature, or submit a pull request with your improvements.


📄 License

This project is licensed under the MIT License.

