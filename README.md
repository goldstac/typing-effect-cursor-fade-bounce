# Typing Effect: Cursor Fade & Bounce

A lightweight, dependency-free HTML/CSS/JavaScript typing animation featuring a blinking cursor with fade-in and bounce effects. Designed for easy integration and customization in modern web projects.

## Features

- Realistic typing animation
- Blinking cursor with fade and bounce transitions
- No dependencies (vanilla JS, HTML, CSS)
- Simple integration and reusable code
- Customizable typing speed, messages, cursor style, and animation

## Usage

Copy the example below into your HTML file. All code (HTML, CSS, and JavaScript) is contained in a single file using `<style>` and `<script>` tags.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Typing Effect: Cursor Fade & Bounce</title>
  <style>
    .typing-container {
      font-family: monospace;
      font-size: 1.5rem;
      white-space: pre;
    }
    .cursor {
      display: inline-block;
      width: 1ch;
      animation: blink 1s steps(1) infinite, bounce 1.5s infinite;
      color: #2196f3;
    }
    @keyframes blink {
      0%, 50% { opacity: 1; }
      51%, 100% { opacity: 0; }
    }
    @keyframes bounce {
      0%, 100% { transform: translateY(0); }
      25% { transform: translateY(-3px); }
      50% { transform: translateY(0); }
      75% { transform: translateY(2px); }
    }
  </style>
</head>
<body>
  <div class="typing-container">
    <span class="typed-text"></span><span class="cursor">|</span>
  </div>
  <script>
    // Typing effect options
    const text = "Welcome to the typing effect!";
    const typingSpeed = 100; // milliseconds per character

    const typedTextSpan = document.querySelector('.typed-text');
    let charIndex = 0;

    function type() {
      if (charIndex < text.length) {
        typedTextSpan.textContent += text.charAt(charIndex);
        charIndex++;
        setTimeout(type, typingSpeed);
      }
    }

    // Start typing effect on page load
    window.onload = type;
  </script>
</body>
</html>
```

### Customization

- **Text:** Change the `text` variable in the script section.
- **Typing Speed:** Adjust the `typingSpeed` value.
- **Cursor Style:** Modify the CSS for `.cursor` as needed.

## License

MIT © [goldstac](https://github.com/goldstac)
