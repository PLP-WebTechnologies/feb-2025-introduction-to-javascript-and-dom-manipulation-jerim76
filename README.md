# Introduction to JavaScript and DOM Manipulation

## Objectives

Write basic JavaScript functions.
Manipulate the DOM dynamically.
Respond to user interactions.

## Instructions

- Create a script.js file and link it to a HTML.
- Structure the document using DOCTYPE, html, head, and body.

>[!NOTE]
>  - Write JavaScript that:
>  - Changes text content dynamically.
>  - Modifies CSS styles via JavaScript.
>  - Adds or removes an element when a button is clicked.


# Tasks
- Create a well-structured HTML5 document.
- Use at least 5 different HTML elements.
- Ensure semantic correctness.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DOM Manipulation Project</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 20px;
            max-width: 800px;
            margin: 0 auto;
            color: #333;
        }

        header {
            text-align: center;
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 1px solid #eee;
        }

        .content-section {
            margin-bottom: 30px;
            padding: 20px;
            border-radius: 5px;
            background-color: #f9f9f9;
        }

        .action-btn {
            padding: 10px 15px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
            margin: 10px 0;
        }

        .action-btn:hover {
            background-color: #45a049;
        }

        .demo-box {
            padding: 20px;
            background-color: #f0f0f0;
            border-radius: 5px;
            transition: all 0.3s ease;
        }

        .special-message {
            padding: 15px;
            background-color: #e7f3fe;
            border-left: 5px solid #2196F3;
            margin-top: 10px;
        }

        .additional-content {
            background-color: #fff;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        footer {
            text-align: center;
            margin-top: 30px;
            padding-top: 20px;
            border-top: 1px solid #eee;
            color: #666;
        }
    </style>
</head>
<body>
    <header>
        <h1 id="main-heading">DOM Manipulation Project</h1>
    </header>
    
    <main>
        <section class="content-section">
            <p id="dynamic-text">This text will change when you click the button below.</p>
            <button id="change-text-btn" class="action-btn">Change Text</button>
        </section>
        
        <section class="content-section">
            <div id="style-demo" class="demo-box">
                This box's style will change when you hover over it.
            </div>
        </section>
        
        <section class="content-section">
            <button id="toggle-element-btn" class="action-btn">Toggle Special Message</button>
            <div id="special-message-container"></div>
        </section>
        
        <article class="additional-content">
            <h2>Additional Information</h2>
            <p>This project demonstrates basic DOM manipulation techniques including:</p>
            <ul>
                <li>Changing text content dynamically</li>
                <li>Modifying CSS styles through JavaScript</li>
                <li>Adding and removing elements</li>
            </ul>
        </article>
    </main>
    
    <footer>
        <p>&copy; 2023 DOM Manipulation Project</p>
    </footer>
    
    <script>
        // Change text content dynamically
        const changeTextBtn = document.getElementById('change-text-btn');
        const dynamicText = document.getElementById('dynamic-text');

        changeTextBtn.addEventListener('click', () => {
            const messages = [
                "Text changed successfully!",
                "You clicked the button!",
                "DOM manipulation is fun!",
                "JavaScript makes websites interactive!",
                "Try hovering over the box below!"
            ];
            
            const randomIndex = Math.floor(Math.random() * messages.length);
            dynamicText.textContent = messages[randomIndex];
            
            // Also change the color for visual feedback
            dynamicText.style.color = getRandomColor();
        });

        // Modify CSS styles via JavaScript
        const styleDemo = document.getElementById('style-demo');

        styleDemo.addEventListener('mouseenter', () => {
            styleDemo.style.backgroundColor = getRandomColor();
            styleDemo.style.transform = 'scale(1.05)';
            styleDemo.style.boxShadow = '0 4px 8px rgba(0, 0, 0, 0.2)';
        });

        styleDemo.addEventListener('mouseleave', () => {
            styleDemo.style.backgroundColor = '#f0f0f0';
            styleDemo.style.transform = 'scale(1)';
            styleDemo.style.boxShadow = 'none';
        });

        // Add or remove an element when a button is clicked
        const toggleElementBtn = document.getElementById('toggle-element-btn');
        const specialMessageContainer = document.getElementById('special-message-container');
        let messageVisible = false;

        toggleElementBtn.addEventListener('click', () => {
            if (messageVisible) {
                // Remove the message
                specialMessageContainer.innerHTML = '';
                toggleElementBtn.textContent = 'Show Special Message';
            } else {
                // Add the message
                const message = document.createElement('div');
                message.className = 'special-message';
                message.innerHTML = `
                    <h3>Special Message!</h3>
                    <p>This element was added dynamically using JavaScript!</p>
                `;
                specialMessageContainer.appendChild(message);
                toggleElementBtn.textContent = 'Hide Special Message';
            }
            
            messageVisible = !messageVisible;
        });

        // Helper function to generate random colors
        function getRandomColor() {
            const letters = '0123456789ABCDEF';
            let color = '#';
            for (let i = 0; i < 6; i++) {
                color += letters[Math.floor(Math.random() * 16)];
            }
            return color;
        }
    </script>
</body>
</html>

Happy Coding! 💻✨
