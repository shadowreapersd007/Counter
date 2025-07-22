<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shadow Reapers D007</title>
    <style>
        /* Dangerous Theme Styles */
        body {
            margin: 0;
            padding: 0;
            font-family: 'Courier New', monospace;
            background-color: #000;
            color: #0f0;
            overflow-x: hidden;
        }
        
        /* Initial Interface - Dangerous Coding Theme */
        #init-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: #000;
            z-index: 1000;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        
        #init-screen h1 {
            color: #f00;
            font-size: 3em;
            text-shadow: 0 0 10px #f00;
            animation: pulse 1s infinite alternate;
        }
        
        #init-screen p {
            color: #0f0;
            text-align: center;
            max-width: 80%;
            margin: 20px auto;
        }
        
        #access-btn {
            background-color: #111;
            color: #0f0;
            border: 1px solid #0f0;
            padding: 12px 40px;
            font-size: 1.3em;
            cursor: pointer;
            transition: all 0.3s;
            margin-top: 30px;
            letter-spacing: 2px;
        }
        
        #access-btn:hover {
            background-color: #0f0;
            color: #000;
            box-shadow: 0 0 20px #0f0;
        }
        
        .matrix-code {
            position: absolute;
            color: #0f0;
            opacity: 0.3;
            font-size: 1.2em;
            user-select: none;
        }
        
        /* Main Interface Styles */
        #main-app {
            display: none;
            padding: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
            border-bottom: 1px solid #333;
            margin-bottom: 25px;
        }
        
        .app-name {
            font-size: 2.2em;
            color: #f00;
            text-shadow: 0 0 8px #f00;
            letter-spacing: 1px;
        }
        
        .counter-owner {
            font-size: 1em;
            color: #0a0;
            opacity: 0.8;
        }
        
        .online-users {
            color: #0f0;
            font-size: 0.9em;
            background-color: #111;
            padding: 5px 10px;
            border-radius: 3px;
        }
        
        /* Tools Navigation */
        .tools-nav {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin: 30px 0;
        }
        
        .tool-btn {
            background-color: #111;
            color: #0f0;
            border: 1px solid #0f0;
            padding: 15px 25px;
            cursor: pointer;
            transition: all 0.3s;
            font-size: 1.1em;
            flex: 1 1 200px;
            text-align: center;
            border-radius: 3px;
        }
        
        .tool-btn:hover {
            background-color: #0f0;
            color: #000;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 255, 0, 0.3);
        }
        
        .tool-btn.active {
            background-color: #0f0;
            color: #000;
            font-weight: bold;
        }
        
        /* Tool Sections */
        .tool-section {
            margin: 30px 0;
            border: 1px solid #333;
            padding: 25px;
            border-radius: 5px;
            display: none;
        }
        
        .tool-section.active {
            display: block;
        }
        
        .tool-title {
            color: #0f0;
            margin-top: 0;
            border-bottom: 1px solid #333;
            padding-bottom: 10px;
            font-size: 1.5em;
        }
        
        .tool-description {
            color: #aaa;
            margin-bottom: 20px;
        }
        
        .tool-options {
            margin: 20px 0;
        }
        
        textarea, input, select, button {
            background-color: #111;
            color: #0f0;
            border: 1px solid #0f0;
            padding: 10px;
            margin: 8px 0;
            width: 100%;
            max-width: 600px;
            font-family: 'Courier New', monospace;
            border-radius: 3px;
        }
        
        button {
            cursor: pointer;
            transition: all 0.3s;
            width: auto;
            padding: 10px 25px;
            font-weight: bold;
        }
        
        button:hover {
            background-color: #0f0;
            color: #000;
            box-shadow: 0 0 10px #0f0;
        }
        
        .result-area {
            margin-top: 25px;
            border: 1px dashed #0f0;
            padding: 20px;
            min-height: 150px;
            white-space: pre-wrap;
            background-color: #0a0a0a;
            border-radius: 3px;
        }
        
        .counter-display {
            font-size: 2em;
            color: #0f0;
            margin: 20px 0;
            text-shadow: 0 0 5px #0f0;
        }
        
        .link-list {
            max-height: 300px;
            overflow-y: auto;
            border: 1px solid #333;
            padding: 10px;
            margin: 10px 0;
        }
        
        .footer {
            margin-top: 50px;
            padding-top: 20px;
            border-top: 1px solid #333;
            font-size: 0.9em;
            text-align: center;
            color: #666;
        }
        
        .footer a {
            color: #0a0;
            text-decoration: none;
            transition: all 0.3s;
        }
        
        .footer a:hover {
            color: #0f0;
            text-decoration: underline;
        }
        
        .about-section {
            margin-top: 40px;
            padding: 20px;
            border: 1px solid #333;
            border-radius: 5px;
        }
        
        @keyframes pulse {
            from { text-shadow: 0 0 5px #f00; }
            to { text-shadow: 0 0 20px #f00, 0 0 30px #f00; }
        }
    </style>
</head>
<body>
    <!-- Initial Dangerous Coding Interface -->
    <div id="init-screen">
        <h1>SHADOW REAPERS D007</h1>
        <p>WARNING: This system contains classified protocols. Unauthorized access prohibited.</p>
        <p>All activities are monitored and recorded. Proceed with caution.</p>
        <button id="access-btn">INITIALIZE SYSTEM</button>
        
        <!-- Matrix rain effect -->
        <div id="matrix-rain"></div>
    </div>
    
    <!-- Main Application Interface -->
    <div id="main-app">
        <div class="header">
            <div>
                <div class="app-name">SHADOW REAPERS D007</div>
                <div class="counter-owner">Counter Owner: Shadow Reapers D007</div>
            </div>
            <div class="online-users">Online Users: <span id="online-users">1</span></div>
        </div>
        
        <!-- Tools Navigation -->
        <div class="tools-nav">
            <div class="tool-btn active" data-tool="repeater">Text Repeater</div>
            <div class="tool-btn" data-tool="counter">Link Counter</div>
            <div class="tool-btn" data-tool="stylish">Stylish Text Maker</div>
            <div class="tool-btn" data-tool="character">Text to Character</div>
        </div>
        
        <!-- Text Repeater Tool -->
        <div class="tool-section active" id="repeater-tool">
            <h2 class="tool-title">TEXT REPEATER TOOL</h2>
            <p class="tool-description">Repeat your text multiple times with different formatting options.</p>
            
            <div class="tool-options">
                <textarea id="repeat-text" placeholder="Enter text to repeat..." rows="6"></textarea>
                <div>
                    <label for="repeat-count">Repeat Count:</label>
                    <select id="repeat-count">
                        <option value="100">100</option>
                        <option value="1000">1K</option>
                        <option value="2000">2K</option>
                        <option value="3000">3K</option>
                        <option value="4000">4K</option>
                        <option value="5000">5K</option>
                        <option value="6000">6K</option>
                        <option value="7000">7K</option>
                        <option value="8000">8K</option>
                        <option value="9000">9K</option>
                        <option value="10000">10K</option>
                        <option value="15000">15K</option>
                        <option value="20000">20K</option>
                    </select>
                </div>
                <div>
                    <label for="repeat-mode">Output Mode:</label>
                    <select id="repeat-mode">
                        <option value="line">New Line for Each</option>
                        <option value="paragraph">Paragraph (with line breaks)</option>
                        <option value="continuous">Continuous (no breaks)</option>
                    </select>
                </div>
                <button id="generate-repeat">GENERATE REPEATED TEXT</button>
            </div>
            <div class="result-area" id="repeat-result"></div>
        </div>
        
        <!-- Link Counter Tool -->
        <div class="tool-section" id="counter-tool">
            <h2 class="tool-title">LINK COUNTER</h2>
            <p class="tool-description">Paste your links below to count them (Max: 100,000 links).</p>
            
            <div class="counter-display">
                Links Counted: <span id="link-counter">0</span>/100,000
            </div>
            
            <div class="tool-options">
                <textarea id="link-input" placeholder="Paste your links here (one per line)..." rows="10"></textarea>
                <button id="count-links">COUNT LINKS</button>
                <button id="clear-links">CLEAR LIST</button>
            </div>
            
            <div class="link-list" id="link-list"></div>
        </div>
        
        <!-- Stylish Text Maker Tool -->
        <div class="tool-section" id="stylish-tool">
            <h2 class="tool-title">STYLISH TEXT MAKER</h2>
            <p class="tool-description">Convert your normal text to stylish, fancy text with different styles.</p>
            
            <div class="tool-options">
                <textarea id="stylish-text" placeholder="Enter text to convert to stylish text..." rows="4"></textarea>
                <div>
                    <label for="text-style">Text Style:</label>
                    <select id="text-style">
                        <option value="bold">Bold</option>
                        <option value="italic">Italic</option>
                        <option value="underline">Underline</option>
                        <option value="strikethrough">Strikethrough</option>
                        <option value="smallcaps">Small Caps</option>
                        <option value="upside">Upside Down</option>
                        <option value="bubble">Bubble Text</option>
                        <option value="gothic">Gothic</option>
                    </select>
                </div>
                <button id="generate-stylish">GENERATE STYLISH TEXT</button>
            </div>
            <div class="result-area" id="stylish-result"></div>
        </div>
        
        <!-- Text to Character Tool -->
        <div class="tool-section" id="character-tool">
            <h2 class="tool-title">TEXT TO CHARACTER</h2>
            <p class="tool-description">Convert text to custom character patterns with spacing options.</p>
            
            <div class="tool-options">
                <textarea id="character-text" placeholder="Enter text to convert to characters..." rows="4"></textarea>
                <div>
                    <label for="character-pattern">Character Pattern:</label>
                    <input type="text" id="character-pattern" value="★" maxlength="3">
                </div>
                <div>
                    <label for="character-repeat">Repeat Pattern:</label>
                    <select id="character-repeat">
                        <option value="1">1 time per character</option>
                        <option value="2">2 times</option>
                        <option value="3">3 times</option>
                        <option value="5">5 times</option>
                        <option value="10">10 times</option>
                    </select>
                </div>
                <div>
                    <label for="character-spacing">Spacing Between:</label>
                    <select id="character-spacing">
                        <option value="0">No space</option>
                        <option value="1" selected>Single space</option>
                        <option value="2">Double space</option>
                        <option value="n">New line</option>
                    </select>
                </div>
                <button id="generate-character">GENERATE CHARACTER TEXT</button>
            </div>
            <div class="result-area" id="character-result"></div>
        </div>
        
        <!-- About Section -->
        <div class="about-section">
            <h3>About Shadow Reapers D007</h3>
            <p>This application works both online and offline. More tools will be coming soon...</p>
            <p>Thank you for using our premium tools!</p>
        </div>
        
        <div class="footer">
            <p>SRD007</p>
            <p>
                Our Telegram channel: <a href="https://t.me/shadowreapersofficialsd007" target="_blank">@shadowreapersofficialsd007</a> | 
                Our Facebook page: <a href="https://www.facebook.com/profile.php?id=61573804311388" target="_blank">Shadow Reapers Official</a>
            </p>
        </div>
    </div>

    <script>
        // Initialize the app
        document.addEventListener('DOMContentLoaded', function() {
            // Create matrix rain effect
            createMatrixRain();
            
            // Online users simulation
            const usersElement = document.getElementById('online-users');
            setInterval(() => {
                const randomUsers = Math.floor(Math.random() * 50) + 1;
                usersElement.textContent = randomUsers;
            }, 3000);
            
            // Initialize button to show main app
            document.getElementById('access-btn').addEventListener('click', function() {
                document.getElementById('init-screen').style.display = 'none';
                document.getElementById('main-app').style.display = 'block';
            });
            
            // Tool navigation
            const toolButtons = document.querySelectorAll('.tool-btn');
            const toolSections = document.querySelectorAll('.tool-section');
            
            toolButtons.forEach(button => {
                button.addEventListener('click', function() {
                    const toolId = this.getAttribute('data-tool');
                    
                    // Update active button
                    toolButtons.forEach(btn => btn.classList.remove('active'));
                    this.classList.add('active');
                    
                    // Show corresponding tool section
                    toolSections.forEach(section => {
                        section.classList.remove('active');
                        if (section.id === `${toolId}-tool`) {
                            section.classList.add('active');
                        }
                    });
                });
            });
            
            // Text repeater tool
            document.getElementById('generate-repeat').addEventListener('click', function() {
                const text = document.getElementById('repeat-text').value.trim();
                const count = parseInt(document.getElementById('repeat-count').value);
                const mode = document.getElementById('repeat-mode').value;
                
                if (!text) {
                    alert('Please enter text to repeat!');
                    return;
                }
                
                let result = '';
                if (mode === 'line') {
                    result = (text + '\n').repeat(count).trim();
                } else if (mode === 'paragraph') {
                    result = (text + '\n\n').repeat(count).trim();
                } else {
                    result = text.repeat(count);
                }
                
                document.getElementById('repeat-result').textContent = result;
            });
            
            // Link counter tool
            const linkInput = document.getElementById('link-input');
            const linkCounter = document.getElementById('link-counter');
            const linkList = document.getElementById('link-list');
            const maxLinks = 100000;
            
            document.getElementById('count-links').addEventListener('click', function() {
                const links = linkInput.value.trim().split('\n').filter(link => link.trim() !== '');
                const count = links.length;
                
                if (count > maxLinks) {
                    alert(`Maximum limit is ${maxLinks.toLocaleString()} links!`);
                    return;
                }
                
                linkCounter.textContent = count.toLocaleString();
                
                // Display the links
                linkList.innerHTML = '';
                links.forEach(link => {
                    const linkElement = document.createElement('div');
                    linkElement.textContent = link;
                    linkElement.style.margin = '5px 0';
                    linkElement.style.padding = '5px';
                    linkElement.style.borderBottom = '1px solid #333';
                    linkList.appendChild(linkElement);
                });
            });
            
            document.getElementById('clear-links').addEventListener('click', function() {
                linkInput.value = '';
                linkCounter.textContent = '0';
                linkList.innerHTML = '';
            });
            
            // Stylish text maker tool
            document.getElementById('generate-stylish').addEventListener('click', function() {
                const text = document.getElementById('stylish-text').value.trim();
                const style = document.getElementById('text-style').value;
                
                if (!text) {
                    alert('Please enter text to convert!');
                    return;
                }
                
                let result = '';
                const boldChars = "𝗔𝗕𝗖𝗗𝗘𝗙𝗚𝗛𝗜𝗝𝗞𝗟𝗠𝗡𝗢𝗣𝗤𝗥𝗦𝗧𝗨𝗩𝗪𝗫𝗬𝗭";
                const italicChars = "𝘈𝘉𝘊𝘋𝘌𝘍𝘎𝘏𝘐𝘑𝘒𝘓𝘔𝘕𝘖𝘗𝘘𝘙𝘚𝘛𝘜𝘝𝘞𝘟𝘠𝘡";
                const underlineChars = "A̲B̲C̲D̲E̲F̲G̲H̲I̲J̲K̲L̲M̲N̲O̲P̲Q̲R̲S̲T̲U̲V̲W̲X̲Y̲Z̲";
                const strikethroughChars = "A̶B̶C̶D̶E̶F̶G̶H̶I̶J̶K̶L̶M̶N̶O̶P̶Q̶R̶S̶T̶U̶V̶W̶X̶Y̶Z̶";
                
                switch(style) {
                    case 'bold':
                        result = text.split('').map(c => {
                            const lower = c.toLowerCase();
                            if (c >= 'A' && c <= 'Z') return boldChars[c.charCodeAt(0) - 65];
                            if (lower >= 'a' && lower <= 'z') return boldChars[lower.charCodeAt(0) - 97];
     <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shadow Reapers D007</title>
    <style>
        /* Dangerous Theme Styles */
        body {
            margin: 0;
            padding: 0;
            font-family: 'Courier New', monospace;
            background-color: #000;
            color: #0f0;
            overflow-x: hidden;
        }
        
        /* Initial Interface - Dangerous Coding Theme */
        #init-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: #000;
            z-index: 1000;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        
        #init-screen h1 {
            color: #f00;
            font-size: 3em;
            text-shadow: 0 0 10px #f00;
            animation: pulse 1s infinite alternate;
        }
        
        #init-screen p {
            color: #0f0;
            text-align: center;
            max-width: 80%;
            margin: 20px auto;
        }
        
        #access-btn {
            background-color: #111;
            color: #0f0;
            border: 1px solid #0f0;
            padding: 12px 40px;
            font-size: 1.3em;
            cursor: pointer;
            transition: all 0.3s;
            margin-top: 30px;
            letter-spacing: 2px;
        }
        
        #access-btn:hover {
            background-color: #0f0;
            color: #000;
            box-shadow: 0 0 20px #0f0;
        }
        
        .matrix-code {
            position: absolute;
            color: #0f0;
            opacity: 0.3;
            font-size: 1.2em;
            user-select: none;
        }
        
        /* Main Interface Styles */
        #main-app {
            display: none;
            padding: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
            border-bottom: 1px solid #333;
            margin-bottom: 25px;
        }
        
        .app-name {
            font-size: 2.2em;
            color: #f00;
            text-shadow: 0 0 8px #f00;
            letter-spacing: 1px;
        }
        
        .counter-owner {
            font-size: 1em;
            color: #0a0;
            opacity: 0.8;
        }
        
        .online-users {
            color: #0f0;
            font-size: 0.9em;
            background-color: #111;
            padding: 5px 10px;
            border-radius: 3px;
        }
        
        /* Tools Navigation */
        .tools-nav {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin: 30px 0;
        }
        
        .tool-btn {
            background-color: #111;
            color: #0f0;
            border: 1px solid #0f0;
            padding: 15px 25px;
            cursor: pointer;
            transition: all 0.3s;
            font-size: 1.1em;
            flex: 1 1 200px;
            text-align: center;
            border-radius: 3px;
        }
        
        .tool-btn:hover {
            background-color: #0f0;
            color: #000;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 255, 0, 0.3);
        }
        
        .tool-btn.active {
            background-color: #0f0;
            color: #000;
            font-weight: bold;
        }
        
        /* Tool Sections */
        .tool-section {
            margin: 30px 0;
            border: 1px solid #333;
            padding: 25px;
            border-radius: 5px;
            display: none;
        }
        
        .tool-section.active {
            display: block;
        }
        
        .tool-title {
            color: #0f0;
            margin-top: 0;
            border-bottom: 1px solid #333;
            padding-bottom: 10px;
            font-size: 1.5em;
        }
        
        .tool-description {
            color: #aaa;
            margin-bottom: 20px;
        }
        
        .tool-options {
            margin: 20px 0;
        }
        
        textarea, input, select, button {
            background-color: #111;
            color: #0f0;
            border: 1px solid #0f0;
            padding: 10px;
            margin: 8px 0;
            width: 100%;
            max-width: 600px;
            font-family: 'Courier New', monospace;
            border-radius: 3px;
        }
        
        button {
            cursor: pointer;
            transition: all 0.3s;
            width: auto;
            padding: 10px 25px;
            font-weight: bold;
        }
        
        button:hover {
            background-color: #0f0;
            color: #000;
            box-shadow: 0 0 10px #0f0;
        }
        
        .result-area {
            margin-top: 25px;
            border: 1px dashed #0f0;
            padding: 20px;
            min-height: 150px;
            white-space: pre-wrap;
            background-color: #0a0a0a;
            border-radius: 3px;
        }
        
        .counter-display {
            font-size: 2em;
            color: #0f0;
            margin: 20px 0;
            text-shadow: 0 0 5px #0f0;
        }
        
        .link-list {
            max-height: 300px;
            overflow-y: auto;
            border: 1px solid #333;
            padding: 10px;
            margin: 10px 0;
        }
        
        .footer {
            margin-top: 50px;
            padding-top: 20px;
            border-top: 1px solid #333;
            font-size: 0.9em;
            text-align: center;
            color: #666;
        }
        
        .footer a {
            color: #0a0;
            text-decoration: none;
            transition: all 0.3s;
        }
        
        .footer a:hover {
            color: #0f0;
            text-decoration: underline;
        }
        
        .about-section {
            margin-top: 40px;
            padding: 20px;
            border: 1px solid #333;
            border-radius: 5px;
        }
        
        @keyframes pulse {
            from { text-shadow: 0 0 5px #f00; }
            to { text-shadow: 0 0 20px #f00, 0 0 30px #f00; }
        }
    </style>
</head>
<body>
    <!-- Initial Dangerous Coding Interface -->
    <div id="init-screen">
        <h1>SHADOW REAPERS D007</h1>
        <p>WARNING: This system contains classified protocols. Unauthorized access prohibited.</p>
        <p>All activities are monitored and recorded. Proceed with caution.</p>
        <button id="access-btn">INITIALIZE SYSTEM</button>
        
        <!-- Matrix rain effect -->
        <div id="matrix-rain"></div>
    </div>
    
    <!-- Main Application Interface -->
    <div id="main-app">
        <div class="header">
            <div>
                <div class="app-name">SHADOW REAPERS D007</div>
                <div class="counter-owner">Counter Owner: Shadow Reapers D007</div>
            </div>
            <div class="online-users">Online Users: <span id="online-users">1</span></div>
        </div>
        
        <!-- Tools Navigation -->
        <div class="tools-nav">
            <div class="tool-btn active" data-tool="repeater">Text Repeater</div>
            <div class="tool-btn" data-tool="counter">Link Counter</div>
            <div class="tool-btn" data-tool="stylish">Stylish Text Maker</div>
            <div class="tool-btn" data-tool="character">Text to Character</div>
        </div>
        
        <!-- Text Repeater Tool -->
        <div class="tool-section active" id="repeater-tool">
            <h2 class="tool-title">TEXT REPEATER TOOL</h2>
            <p class="tool-description">Repeat your text multiple times with different formatting options.</p>
            
            <div class="tool-options">
                <textarea id="repeat-text" placeholder="Enter text to repeat..." rows="6"></textarea>
                <div>
                    <label for="repeat-count">Repeat Count:</label>
                    <select id="repeat-count">
                        <option value="100">100</option>
                        <option value="1000">1K</option>
                        <option value="2000">2K</option>
                        <option value="3000">3K</option>
                        <option value="4000">4K</option>
                        <option value="5000">5K</option>
                        <option value="6000">6K</option>
                        <option value="7000">7K</option>
                        <option value="8000">8K</option>
                        <option value="9000">9K</option>
                        <option value="10000">10K</option>
                        <option value="15000">15K</option>
                        <option value="20000">20K</option>
                    </select>
                </div>
                <div>
                    <label for="repeat-mode">Output Mode:</label>
                    <select id="repeat-mode">
                        <option value="line">New Line for Each</option>
                        <option value="paragraph">Paragraph (with line breaks)</option>
                        <option value="continuous">Continuous (no breaks)</option>
                    </select>
                </div>
                <button id="generate-repeat">GENERATE REPEATED TEXT</button>
            </div>
            <div class="result-area" id="repeat-result"></div>
        </div>
        
        <!-- Link Counter Tool -->
        <div class="tool-section" id="counter-tool">
            <h2 class="tool-title">LINK COUNTER</h2>
            <p class="tool-description">Paste your links below to count them (Max: 100,000 links).</p>
            
            <div class="counter-display">
                Links Counted: <span id="link-counter">0</span>/100,000
            </div>
            
            <div class="tool-options">
                <textarea id="link-input" placeholder="Paste your links here (one per line)..." rows="10"></textarea>
                <button id="count-links">COUNT LINKS</button>
                <button id="clear-links">CLEAR LIST</button>
            </div>
            
            <div class="link-list" id="link-list"></div>
        </div>
        
        <!-- Stylish Text Maker Tool -->
        <div class="tool-section" id="stylish-tool">
            <h2 class="tool-title">STYLISH TEXT MAKER</h2>
            <p class="tool-description">Convert your normal text to stylish, fancy text with different styles.</p>
            
            <div class="tool-options">
                <textarea id="stylish-text" placeholder="Enter text to convert to stylish text..." rows="4"></textarea>
                <div>
                    <label for="text-style">Text Style:</label>
                    <select id="text-style">
                        <option value="bold">Bold</option>
                        <option value="italic">Italic</option>
                        <option value="underline">Underline</option>
                        <option value="strikethrough">Strikethrough</option>
                        <option value="smallcaps">Small Caps</option>
                        <option value="upside">Upside Down</option>
                        <option value="bubble">Bubble Text</option>
                        <option value="gothic">Gothic</option>
                    </select>
                </div>
                <button id="generate-stylish">GENERATE STYLISH TEXT</button>
            </div>
            <div class="result-area" id="stylish-result"></div>
        </div>
        
        <!-- Text to Character Tool -->
        <div class="tool-section" id="character-tool">
            <h2 class="tool-title">TEXT TO CHARACTER</h2>
            <p class="tool-description">Convert text to custom character patterns with spacing options.</p>
            
            <div class="tool-options">
                <textarea id="character-text" placeholder="Enter text to convert to characters..." rows="4"></textarea>
                <div>
                    <label for="character-pattern">Character Pattern:</label>
                    <input type="text" id="character-pattern" value="★" maxlength="3">
                </div>
                <div>
                    <label for="character-repeat">Repeat Pattern:</label>
                    <select id="character-repeat">
                        <option value="1">1 time per character</option>
                        <option value="2">2 times</option>
                        <option value="3">3 times</option>
                        <option value="5">5 times</option>
                        <option value="10">10 times</option>
                    </select>
                </div>
                <div>
                    <label for="character-spacing">Spacing Between:</label>
                    <select id="character-spacing">
                        <option value="0">No space</option>
                        <option value="1" selected>Single space</option>
                        <option value="2">Double space</option>
                        <option value="n">New line</option>
                    </select>
                </div>
                <button id="generate-character">GENERATE CHARACTER TEXT</button>
            </div>
            <div class="result-area" id="character-result"></div>
        </div>
        
        <!-- About Section -->
        <div class="about-section">
            <h3>About Shadow Reapers D007</h3>
            <p>This application works both online and offline. More tools will be coming soon...</p>
            <p>Thank you for using our premium tools!</p>
        </div>
        
        <div class="footer">
            <p>SRD007</p>
            <p>
                Our Telegram channel: <a href="https://t.me/shadowreapersofficialsd007" target="_blank">@shadowreapersofficialsd007</a> | 
                Our Facebook page: <a href="https://www.facebook.com/profile.php?id=61573804311388" target="_blank">Shadow Reapers Official</a>
            </p>
        </div>
    </div>

    <script>
        // Initialize the app
        document.addEventListener('DOMContentLoaded', function() {
            // Create matrix rain effect
            createMatrixRain();
            
            // Online users simulation
            const usersElement = document.getElementById('online-users');
            setInterval(() => {
                const randomUsers = Math.floor(Math.random() * 50) + 1;
                usersElement.textContent = randomUsers;
            }, 3000);
            
            // Initialize button to show main app
            document.getElementById('access-btn').addEventListener('click', function() {
                document.getElementById('init-screen').style.display = 'none';
                document.getElementById('main-app').style.display = 'block';
            });
            
            // Tool navigation
            const toolButtons = document.querySelectorAll('.tool-btn');
            const toolSections = document.querySelectorAll('.tool-section');
            
            toolButtons.forEach(button => {
                button.addEventListener('click', function() {
                    const toolId = this.getAttribute('data-tool');
                    
                    // Update active button
                    toolButtons.forEach(btn => btn.classList.remove('active'));
                    this.classList.add('active');
                    
                    // Show corresponding tool section
                    toolSections.forEach(section => {
                        section.classList.remove('active');
                        if (section.id === `${toolId}-tool`) {
                            section.classList.add('active');
                        }
                    });
                });
            });
            
            // Text repeater tool
            document.getElementById('generate-repeat').addEventListener('click', function() {
                const text = document.getElementById('repeat-text').value.trim();
                const count = parseInt(document.getElementById('repeat-count').value);
                const mode = document.getElementById('repeat-mode').value;
                
                if (!text) {
                    alert('Please enter text to repeat!');
                    return;
                }
                
                let result = '';
                if (mode === 'line') {
                    result = (text + '\n').repeat(count).trim();
                } else if (mode === 'paragraph') {
                    result = (text + '\n\n').repeat(count).trim();
                } else {
                    result = text.repeat(count);
                }
                
                document.getElementById('repeat-result').textContent = result;
            });
            
            // Link counter tool
            const linkInput = document.getElementById('link-input');
            const linkCounter = document.getElementById('link-counter');
            const linkList = document.getElementById('link-list');
            const maxLinks = 100000;
            
            document.getElementById('count-links').addEventListener('click', function() {
                const links = linkInput.value.trim().split('\n').filter(link => link.trim() !== '');
                const count = links.length;
                
                if (count > maxLinks) {
                    alert(`Maximum limit is ${maxLinks.toLocaleString()} links!`);
                    return;
                }
                
                linkCounter.textContent = count.toLocaleString();
                
                // Display the links
                linkList.innerHTML = '';
                links.forEach(link => {
                    const linkElement = document.createElement('div');
                    linkElement.textContent = link;
                    linkElement.style.margin = '5px 0';
                    linkElement.style.padding = '5px';
                    linkElement.style.borderBottom = '1px solid #333';
                    linkList.appendChild(linkElement);
                });
            });
            
            document.getElementById('clear-links').addEventListener('click', function() {
                linkInput.value = '';
                linkCounter.textContent = '0';
                linkList.innerHTML = '';
            });
            
            // Stylish text maker tool
            document.getElementById('generate-stylish').addEventListener('click', function() {
                const text = document.getElementById('stylish-text').value.trim();
                const style = document.getElementById('text-style').value;
                
                if (!text) {
                    alert('Please enter text to convert!');
                    return;
                }
                
                let result = '';
                const boldChars = "𝗔𝗕𝗖𝗗𝗘𝗙𝗚𝗛𝗜𝗝𝗞𝗟𝗠𝗡𝗢𝗣𝗤𝗥𝗦𝗧𝗨𝗩𝗪𝗫𝗬𝗭";
                const italicChars = "𝘈𝘉𝘊𝘋𝘌𝘍𝘎𝘏𝘐𝘑𝘒𝘓𝘔𝘕𝘖𝘗𝘘𝘙𝘚𝘛𝘜𝘝𝘞𝘟𝘠𝘡";
                const underlineChars = "A̲B̲C̲D̲E̲F̲G̲H̲I̲J̲K̲L̲M̲N̲O̲P̲Q̲R̲S̲T̲U̲V̲W̲X̲Y̲Z̲";
                const strikethroughChars = "A̶B̶C̶D̶E̶F̶G̶H̶I̶J̶K̶L̶M̶N̶O̶P̶Q̶R̶S̶T̶U̶V̶W̶X̶Y̶Z̶";
                
                switch(style) {
                    case 'bold':
                        result = text.split('').map(c => {
                            const lower = c.toLowerCase();
                            if (c >= 'A' && c <= 'Z') return boldChars[c.charCodeAt(0) - 65];
                            if (lower >= 'a' && lower <= 'z') return boldChars[lower.charCodeAt(0) - 97];
     
