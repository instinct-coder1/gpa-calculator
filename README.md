# Vintage CGPA Calculator

A retro 1980s-style CGPA / SGPA calculator built with plain HTML, CSS and JavaScript. No build step, no dependencies, no installation.

## Features
- Unlimited semesters, each with unlimited subjects (name, credits, grade)
- Live SGPA per semester and overall CGPA on a green LCD display
- 10-point (O, A+, A ... F) and 4-point (A ... F) grade scales
- Total credits, approximate percentage and class (Distinction / First Class / ...)
- "Prior CGPA" option to add results from earlier semesters without re-entering them
- Auto-saves in your browser (localStorage)
- Print-friendly "tape" output
- Works on mobile and desktop

## Project structure
```
gpa-calculator/
├── index.html   # page layout
├── style.css    # vintage calculator styling
├── script.js    # CGPA logic
└── README.md
```

## Run it on your machine

You only need a web browser (Chrome, Edge, Firefox, Safari). Git is needed only if you want to clone with the terminal.

### Option 1: Clone and run from the terminal

1. Clone the repo:
   ```bash
   git clone https://github.com/instinct-coder1/gpa-calculator.git
   ```
2. Go into the folder:
   ```bash
   cd gpa-calculator
   ```
3. Open the app in your browser:

   | System | Command |
   |---|---|
   | Windows (CMD / PowerShell) | `start index.html` |
   | macOS | `open index.html` |
   | Linux | `xdg-open index.html` |

   You can also double-click `index.html` in your file manager.

### Option 2: Run with a local server (optional)

Use this if you prefer to view it at `http://localhost`.

With Python (already installed on most computers):
```bash
python3 -m http.server 8000
```
On Windows, use `python -m http.server 8000` if `python3` is not found.

With Node.js:
```bash
npx serve .
```

Then open **http://localhost:8000** (or the address `serve` prints) in your browser. Press `Ctrl + C` in the terminal to stop the server.

### Option 3: Open in a code editor

**VS Code**
1. Clone the repo (see Option 1), then run:
   ```bash
   code gpa-calculator
   ```
   Or use File → Open Folder and select the `gpa-calculator` folder.
2. Install the **Live Server** extension (by Ritwick Dey) from the Extensions tab.
3. Right-click `index.html` and choose **Open with Live Server**. The page opens in your browser and reloads whenever you save a file.

**Other editors** (Sublime Text, Notepad++, WebStorm, Atom, etc.)
1. Open the `gpa-calculator` folder in your editor.
2. Edit `index.html`, `style.css` or `script.js` as you like.
3. Open `index.html` in your browser and refresh the page (`F5`) after saving changes.

### Option 4: No Git? Download the ZIP
1. On the GitHub repo page, click the green **Code** button, then **Download ZIP**.
2. Extract the ZIP.
3. Open `index.html` in your browser.

## How to use the calculator
1. Enter each subject's name, credits and grade in the semester card.
2. Click **+ Subject** to add more subjects, or **+ SEMESTER** to add another semester.
3. The LCD shows your overall CGPA, total credits, approximate percentage and class. Each semester card shows its own SGPA.
4. Click **SCALE** to switch between the 10-point and 4-point grading systems. Switching clears the selected grades.
5. Click **PRIOR CGPA** to enter a previous CGPA and credit total from earlier semesters.
6. Click **ALL CLEAR** to reset everything.

## Formula
```
CGPA = Σ (credits × grade points) / Σ credits
```
- A grade of `F` counts as 0 points, but its credits are still included.
- Percentage is `CGPA × 9.5` on the 10-point scale (a common Indian conversion) and `CGPA / 4 × 100` on the 4-point scale. Check your university's own rule and edit the `pct` line in `script.js` if it differs.

## Troubleshooting
- **Fonts look plain:** the retro fonts load from Google Fonts, so connect to the internet once. The calculator still works without them.
- **Data disappeared:** data is saved per browser. Clearing site data or using private mode removes it.
- **`git` is not recognized:** install Git from https://git-scm.com or use Option 4.

## Contributing
1. Fork the repo
2. Create a branch: `git checkout -b my-feature`
3. Commit your changes: `git commit -m "Add my feature"`
4. Push the branch: `git push origin my-feature`
5. Open a Pull Request

## License
Free to use and modify for learning and personal projects.
