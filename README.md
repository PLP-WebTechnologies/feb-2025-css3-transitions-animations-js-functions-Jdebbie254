# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.

Happy Coding! 💻✨

index.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Web Experience</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Interactive Web Experience</h1>
        <p>Featuring CSS animations, JavaScript functions, and localStorage</p>
    </header>

    <main>
        <!-- Theme Selector Section -->
        <section class="card">
            <h2>Theme Preferences</h2>
            <div class="theme-options">
                <button class="theme-btn light" data-theme="light">Light</button>
                <button class="theme-btn dark" data-theme="dark">Dark</button>
                <button class="theme-btn blue" data-theme="blue">Blue</button>
            </div>
            <p>Your preference will be saved for your next visit!</p>
        </section>

        <!-- Animation Trigger Section -->
        <section class="card">
            <h2>Animation Playground</h2>
            <button id="animate-btn" class="pulse">Click to Animate</button>
            <div id="animation-box" class="animation-box">
                <div class="animation-object"></div>
            </div>
        </section>

        <!-- Counter with LocalStorage -->
        <section class="card">
            <h2>Visit Counter</h2>
            <div class="counter-container">
                <p>You've interacted with this page:</p>
                <div id="counter" class="counter">0</div>
                <p>times</p>
            </div>
            <button id="reset-counter">Reset Counter</button>
        </section>

        <!-- User Notes Section -->
        <section class="card">
            <h2>Notes</h2>
            <textarea id="user-notes" placeholder="Type your notes here..."></textarea>
            <p>Your notes will be automatically saved</p>
        </section>
    </main>

    <footer>
        <p>Created with ❤️ using HTML, CSS, and JavaScript</p>
    </footer>

    <script src="script.js"></script>
</body>
</html>

styles.css
/* Base Styles */
:root {
    --primary-color: #3498db;
    --secondary-color: #2ecc71;
    --text-color: #333;
    --bg-color: #f9f9f9;
    --card-color: #fff;
    --shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

[data-theme="dark"] {
    --primary-color: #9b59b6;
    --secondary-color: #1abc9c;
    --text-color: #ecf0f1;
    --bg-color: #2c3e50;
    --card-color: #34495e;
    --shadow: 0 4px 6px rgba(0, 0, 0, 0.3);
}

[data-theme="blue"] {
    --primary-color: #2980b9;
    --secondary-color: #e74c3c;
    --text-color: #ecf0f1;
    --bg-color: #3498db;
    --card-color: #2980b9;
    --shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: var(--bg-color);
    color: var(--text-color);
    line-height: 1.6;
    margin: 0;
    padding: 20px;
    transition: background-color 0.5s ease, color 0.5s ease;
}

header, main, footer {
    max-width: 1000px;
    margin: 0 auto;
}

header {
    text-align: center;
    margin-bottom: 30px;
    padding: 20px 0;
}

h1, h2 {
    color: var(--primary-color);
}

/* Card Styles */
.card {
    background-color: var(--card-color);
    border-radius: 10px;
    padding: 20px;
    margin-bottom: 30px;
    box-shadow: var(--shadow);
    transition: all 0.5s ease;
}

/* Button Styles */
button {
    background-color: var(--primary-color);
    color: white;
    border: none;
    padding: 10px 20px;
    border-radius: 5px;
    cursor: pointer;
    font-size: 16px;
    transition: all 0.3s ease;
    margin: 5px;
}

button:hover {
    transform: translateY(-2px);
    box-shadow: 0 6px 8px rgba(0, 0, 0, 0.15);
}

.theme-btn {
    width: 80px;
}

.light { background-color: #f1c40f; }
.dark { background-color: #34495e; }
.blue { background-color: #3498db; }

/* Animation Styles */
.pulse {
    animation: pulse 2s infinite;
}

@keyframes pulse {
    0% { transform: scale(1); }
    50% { transform: scale(1.05); }
    100% { transform: scale(1); }
}

.animation-box {
    width: 100%;
    height: 200px;
    background-color: #ecf0f1;
    border-radius: 8px;
    margin: 20px 0;
    position: relative;
    overflow: hidden;
}

.animation-object {
    width: 50px;
    height: 50px;
    background-color: var(--secondary-color);
    border-radius: 50%;
    position: absolute;
    top: 50%;
    left: 0;
    transform: translateY(-50%);
}

/* Animation Classes */
.bounce {
    animation: bounce 2s infinite alternate;
}

@keyframes bounce {
    from { left: 0; }
    to { left: calc(100% - 50px); }
}

.spin {
    animation: spin 1s linear infinite;
}

@keyframes spin {
    from { transform: translateY(-50%) rotate(0deg); }
    to { transform: translateY(-50%) rotate(360deg); }
}

.color-change {
    animation: colorChange 3s infinite alternate;
}

@keyframes colorChange {
    0% { background-color: var(--secondary-color); }
    25% { background-color: #e74c3c; }
    50% { background-color: #9b59b6; }
    75% { background-color: #f1c40f; }
    100% { background-color: #1abc9c; }
}

/* Counter Styles */
.counter-container {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    margin: 20px 0;
}

.counter {
    font-size: 2rem;
    font-weight: bold;
    color: var(--secondary-color);
    min-width: 50px;
    text-align: center;
    transition: transform 0.3s ease;
}

.counter.animate {
    transform: scale(1.2);
    color: var(--primary-color);
}

/* Textarea Styles */
#user-notes {
    width: 100%;
    height: 150px;
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 5px;
    font-family: inherit;
    font-size: 16px;
    resize: vertical;
    margin-bottom: 10px;
    transition: border-color 0.3s ease;
}

#user-notes:focus {
    border-color: var(--primary-color);
    outline: none;
}

/* Footer Styles */
footer {
    text-align: center;
    padding: 20px;
    margin-top: 40px;
    color: var(--text-color);
}

script.js
document.addEventListener('DOMContentLoaded', function() {
    // ========== Theme Selection with localStorage ==========
    const themeButtons = document.querySelectorAll('.theme-btn');
    const body = document.body;
    
    // Check for saved theme preference
    const savedTheme = localStorage.getItem('theme');
    if (savedTheme) {
        body.setAttribute('data-theme', savedTheme);
    }
    
    // Theme button event listeners
    themeButtons.forEach(button => {
        button.addEventListener('click', function() {
            const theme = this.getAttribute('data-theme');
            body.setAttribute('data-theme', theme);
            localStorage.setItem('theme', theme);
            
            // Add visual feedback
            themeButtons.forEach(btn => btn.style.transform = 'translateY(0)');
            this.style.transform = 'translateY(-5px)';
        });
    });
    
    // ========== Animation Trigger ==========
    const animateBtn = document.getElementById('animate-btn');
    const animationBox = document.getElementById('animation-box');
    const animationObject = document.querySelector('.animation-object');
    
    const animations = ['bounce', 'spin', 'color-change'];
    let currentAnimation = 0;
    
    animateBtn.addEventListener('click', function() {
        // Remove all animation classes
        animationObject.classList.remove(...animations);
        
        // Add the next animation
        animationObject.classList.add(animations[currentAnimation]);
        
        // Update animation index
        currentAnimation = (currentAnimation + 1) % animations.length;
        
        // Add click effect
        this.classList.add('clicked');
        setTimeout(() => {
            this.classList.remove('clicked');
        }, 300);
    });
    
    // ========== Visit Counter with localStorage ==========
    const counterElement = document.getElementById('counter');
    const resetCounterBtn = document.getElementById('reset-counter');
    
    // Initialize or increment counter
    let visitCount = localStorage.getItem('visitCount') || 0;
    visitCount++;
    localStorage.setItem('visitCount', visitCount);
    counterElement.textContent = visitCount;
    
    // Animate counter on load
    counterElement.classList.add('animate');
    setTimeout(() => {
        counterElement.classList.remove('animate');
    }, 1000);
    
    // Reset counter
    resetCounterBtn.addEventListener('click', function() {
        visitCount = 0;
        localStorage.setItem('visitCount', visitCount);
        counterElement.textContent = visitCount;
        counterElement.classList.add('animate');
        setTimeout(() => {
            counterElement.classList.remove('animate');
        }, 1000);
    });
    
    // ========== User Notes with Auto-Save ==========
    const userNotes = document.getElementById('user-notes');
    
    // Load saved notes
    const savedNotes = localStorage.getItem('userNotes');
    if (savedNotes) {
        userNotes.value = savedNotes;
    }
    
    // Auto-save notes
    userNotes.addEventListener('input', function() {
        localStorage.setItem('userNotes', this.value);
        
        // Show save indicator
        const saveIndicator = document.createElement('div');
        saveIndicator.textContent = 'Saved!';
        saveIndicator.style.position = 'absolute';
        saveIndicator.style.right = '10px';
        saveIndicator.style.bottom = '10px';
        saveIndicator.style.color = 'green';
        saveIndicator.style.fontSize = '12px';
        saveIndicator.style.opacity = '0';
        saveIndicator.style.transition = 'opacity 0.3s';
        
        const existingIndicator = this.parentNode.querySelector('.save-indicator');
        if (existingIndicator) {
            existingIndicator.remove();
        }
        
        this.parentNode.appendChild(saveIndicator);
        
        setTimeout(() => {
            saveIndicator.style.opacity = '1';
        }, 10);
        
        setTimeout(() => {
            saveIndicator.style.opacity = '0';
            setTimeout(() => {
                saveIndicator.remove();
            }, 300);
        }, 2000);
    });
    
    // ========== Additional Animation Effects ==========
    // Add hover effect to cards
    const cards = document.querySelectorAll('.card');
    cards.forEach(card => {
        card.addEventListener('mouseenter', function() {
            this.style.transform = 'translateY(-5px)';
            this.style.boxShadow = '0 10px 15px rgba(0, 0, 0, 0.15)';
        });
        
        card.addEventListener('mouseleave', function() {
            this.style.transform = 'translateY(0)';
            this.style.boxShadow = 'var(--shadow)';
        });
    });
});
