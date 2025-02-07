

### Repository Structure:
```
/
├── experiments/
│   ├── endless-button/
│   │   ├── index.html
│   │   ├── style.css
│   │   └── script.js
│   ├── fake-loading/
│   │   ├── index.html
│   │   └── script.js
│   ├── annoying-popups/
│   │   ├── index.html
│   │   └── script.js
│   └── ... (other experiments)
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

### Sample Code Snippets:

**1. Endless Button** (`endless-button/index.html`):
```html
<!DOCTYPE html>
<html>
<head>
  <title>Endless Button</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      background: #ffcccc;
    }
    #runaway-btn {
      padding: 20px 40px;
      font-size: 1.5em;
      cursor: pointer;
      transition: all 0.3s ease;
    }
  </style>
</head>
<body>
  <button id="runaway-btn">Click Me If You Can!</button>
  <script>
    const btn = document.getElementById('runaway-btn');
    
    btn.addEventListener('mouseover', () => {
      btn.style.transform = `translate(
        ${Math.random() * 200 - 100}px,
        ${Math.random() * 200 - 100}px
      )`;
    });

    btn.addEventListener('click', () => {
      btn.style.transform = 'translate(0, 0)';
      btn.innerText = ['Nope!', 'Try Harder!', 'Missed!', 'Almost!'][Math.floor(Math.random()*4)];
    });
  </script>
</body>
</html>
```

**2. Fake Loading Screen** (`fake-loading/index.html`):
```html
<!DOCTYPE html>
<html>
<head>
  <title>Never-ending Load</title>
  <style>
    .loader {
      width: 200px;
      height: 20px;
      background: #eee;
      margin: 100px auto;
      border-radius: 10px;
      overflow: hidden;
    }
    
    .progress {
      width: 0%;
      height: 100%;
      background: #4CAF50;
      transition: width 0.3s ease;
    }
  </style>
</head>
<body>
  <div class="loader">
    <div class="progress"></div>
  </div>
  <h2 style="text-align: center">Loading important stuff... 0%</h2>

  <script>
    let progress = 0;
    const progressBar = document.querySelector('.progress');
    const text = document.querySelector('h2');

    setInterval(() => {
      progress = Math.min(99.9, progress + Math.random() * 5);
      progressBar.style.width = `${progress}%`;
      text.innerText = `Loading important stuff... ${progress.toFixed(1)}%`;
    }, 1000);
  </script>
</body>
</html>
```

### README.md Suggestions:
```markdown
# Useless Web Experiments 🎮

A collection of completely pointless but strangely addictive web experiments.

## Experiments List
- 🏃 Endless Button
- ⏳ Fake Loading Screen
- 🚨 Annoying Popups
- 🕰️ Unpredictable Clock
- 🤖 Fake Hacking Console
- ... (add more as you create them)

## How to Use
1. Clone the repo
2. Open any experiment's `index.html` in your browser

## Contributing
Add your own useless experiment! See [CONTRIBUTING.md](CONTRIBUTING.md)

## License
MIT License - go crazy with these ideas!
```

### Suggested Tech Stack:
1. **Core**: Vanilla JavaScript (for simplicity)
2. **Styling**: 
   - Tailwind CSS (for quick utility-first styling)
   - CSS Animations
3. **Enhancements**:
   - GSAP for complex animations
   - React for more complex state management
   - Webpack for bundling (if using React)
