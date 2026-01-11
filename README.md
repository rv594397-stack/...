<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>tu pagal h behuda aurat</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        /* General Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #000;
            color: white; /* Fixed color */
            font-family: 'Poppins', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            overflow: hidden;
        }

        /* Container */
        .container {
            width: 100%;
            max-width: 400px;
            height: 100vh;
            position: relative;
            background: radial-gradient(circle, rgba(50,0,50,0.5) 0%, #000 100%); /* Fixed gradient */
            overflow-y: auto;
            text-align: center;
            padding: 20px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center; 
        }

        /* Utility Classes */
        .hidden {
            display: none !important;
        }

        /* --- FIXED BUNNY IMAGE STYLES --- */
        .cute-gif {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            object-fit: cover;
            border: 4px solid #ff4d6d;
            margin-bottom: 20px;
            box-shadow: 0 0 20px rgba(255, 77, 109, 0.5);
            display: block; 
        }

        /* Typography */
        h1 {
            font-family: 'Dancing Script', cursive;
            font-size: 2.5rem;
            color: #ff4d6d;
            margin-bottom: 10px;
        }

        p {
            font-size: 1rem;
            color: #ddd;
            margin-bottom: 30px;
            line-height: 1.5;
        }

        /* Buttons */
        .btn {
            padding: 12px 30px;
            font-size: 1.1rem;
            background: linear-gradient(45deg, #ff4d6d, #ff8fa3);
            border: none;
            border-radius: 25px;
            color: white;
            font-weight: 600;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(255, 77, 109, 0.4);
            transition: transform 0.2s;
        }

        .btn:active {
            transform: scale(0.95);
        }

        /* Progress Bar */
        .progress-container {
            width: 80%;
            height: 20px;
            background: #333;
            border-radius: 10px;
            margin: 20px auto;
            overflow: hidden;
        }

        .progress-bar {
            height: 100%;
            width: 0%;
            background: linear-gradient(90deg, #ff4d6d, #ff758c);
            transition: width 0.1s linear;
        }

        .status-text {
            font-size: 1.2rem;
            font-weight: bold;
            margin-bottom: 10px;
        }

        .warning-msg {
            color: #ffd700;
            font-weight: bold;
            margin-top: 15px;
            font-size: 0.9rem;
            display: none;
            animation: blink 0.5s infinite alternate;
        }

        @keyframes blink {
            from { opacity: 1; }
            to { opacity: 0.5; }
        }

        /* Compliments List */
        .compliment-list {
            display: flex;
            flex-direction: column;
            gap: 15px;
            width: 100%;
        }

        .compliment-item {
            background: rgba(255, 255, 255, 0.1);
            padding: 15px;
            border-radius: 15px;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 77, 109, 0.3);
            position: relative;
            overflow: hidden;
        }

        .compliment-item.revealed {
            background: linear-gradient(45deg, #ff4d6d, #ff8fa3);
            transform: scale(1.02);
        }

        .compliment-text {
            display: none;
            font-weight: 500;
            color: white;
        }

        .heart-icon {
            font-size: 1.2rem;
        }

        /* Note Container */
        .note-container {
            background: #fff;
            color: #333;
            padding: 30px;
            border-radius: 20px;
            width: 90%;
            margin: 0 auto;
            position: relative;
            transform: rotate(-2deg);
            box-shadow: 0 0 20px rgba(255,255,255,0.2);
            min-height: 300px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        .note-content {
            font-family: 'Poppins', sans-serif;
            font-size: 0.95rem;
            line-height: 1.6;
            text-align: left;
            width: 100%;
        }

        .typewriter-text {
            border-right: 2px solid #ff4d6d;
            white-space: pre-wrap;
            animation: blinkCursor 0.7s infinite;
        }

        @keyframes blinkCursor {
            50% { border-color: transparent; }
        }

        .envelope-icon {
            font-size: 4rem;
            color: #ff4d6d;
            cursor: pointer;
            animation: float 2s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

    </style>
</head>
<body>

    <div class="bg-dots"></div>

    <div class="container" id="screen1">
        <img src="https://i.pinimg.com/originals/f6/a7/68/f6a7681648a97b27878696009831c773.gif" alt="Cute Bear" class="cute-gif">
        <h1>helo babu </h1>
        <p>Do you ki tu kitii pagal h ?</p>
        <button class="btn" onclick="goToScreen2()">Open your khopdi 💐</button>
    </div>

    <div class="container hidden" id="screen2">
        <h1 style="font-size: 1.8rem;">Measuring your madness...</h1>
        <div class="progress-container">
            <div class="progress-bar" id="progressBar"></div>
        </div>
        <div class="status-text" id="statusText">0%</div>
        <div class="warning-msg" id="warningMsg">⚠️ WARNING: TOO MAD TO HANDLE</div>
    </div>

    <div class="container hidden" id="screen3">
        <div style="font-size: 3rem; margin-bottom: 10px;">HEHE 🫶</div>
        <h1>Sirf tere liye hi h </h1>
        <p>Tap each one to reveal</p>
        
        <div class="compliment-list">
            <div class="compliment-item" onclick="reveal(this, 'TU KITII ACHII H YRRR! ')">
                <span class="heart-icon">👀</span>
                <span class="compliment-text"></span>
            </div>
            <div class="compliment-item" onclick="reveal(this, 'TU PAGAL BHI H!')">
                <span class="heart-icon">💝</span>
                <span class="compliment-text"></span>
            </div>
            <div class="compliment-item" onclick="reveal(this, 'TU CUTE TO H! ')">
                <span class="heart-icon">💐</span>
                <span class="compliment-text"></span>
            </div>
            <div class="compliment-item" onclick="reveal(this, 'PAR TERA BF  NHI H! ')">
                <span class="heart-icon">🫠</span>
                <span class="compliment-text"></span>
            </div>
            <div class="compliment-item" onclick="reveal(this, 'CHL AB JYDAYA KHUSH MT HO ')">
                <span class="heart-icon">💞</span>
                <span class="compliment-text"></span>
            </div>
        </div>

        <button class="btn" style="margin-top: 20px;" onclick="goToScreen4()">See more👀 -></button>
    </div>

    <div class="container hidden" id="screen4">
        <h1>A little note for you</h1>
        <br>
        <div id="envelope" onclick="openLetter()">
            <div class="envelope-icon">💌🎀</div>
            <p>Tap to open☠️</p>
        </div>
        
        <div class="note-container hidden" id="notePaper">
            <div class="note-content">
                <span id="typedText"></span><span class="cursor">|</span>
            </div>
        </div>

        <button class="btn hidden" id="finalBtn" style="margin-top: 20px;" onclick="goToScreen5()">RUK RUK ABHI KUCH BAKI H -></button>
    </div>

    <div class="container hidden" id="screen5">
        <img src="https://i.pinimg.com/originals/5f/5c/42/5f5c42337d45761a29272338271701a2.gif" alt="Cute Hug" class="cute-gif">
        <h1>You'll always be special to me</h1>
    </div>

    <script>
        // Navigation Functions
        function goToScreen2() {
            document.getElementById('screen1').classList.add('hidden');
            document.getElementById('screen2').classList.remove('hidden');
            startProgress();
        }

        function goToScreen4() {
            document.getElementById('screen3').classList.add('hidden');
            document.getElementById('screen4').classList.remove('hidden');
        }

        function goToScreen5() {
            document.getElementById('screen4').classList.add('hidden');
            document.getElementById('screen5').classList.remove('hidden');
        }

        // Screen 2 Logic: Progress Bar
        function startProgress() {
            let width = 0;
            const bar = document.getElementById('progressBar');
            const text = document.getElementById('statusText');
            const warning = document.getElementById('warningMsg');

            const interval = setInterval(() => {
                if (width >= 120) {
                    clearInterval(interval);
                    warning.style.display = 'block';
                    setTimeout(() => {
                        document.getElementById('screen2').classList.add('hidden');
                        document.getElementById('screen3').classList.remove('hidden');
                    }, 2500); // Wait 2.5s before next screen
                } else {
                    width++;
                    bar.style.width = width + '%';
                    text.innerText = width + '%';
                    
                    if(width === 70 || width === 90) {
                        width += 0; 
                    }
                }
            }, 30); 
        }

        // Screen 3 Logic: Reveal Text
        function reveal(element, text) {
            if (!element.classList.contains('revealed')) {
                element.classList.add('revealed');
                element.querySelector('.heart-icon').style.display = 'none';
                const textSpan = element.querySelector('.compliment-text');
                textSpan.innerText = text;
                textSpan.style.display = 'block';
            }
        }

        // Screen 4 Logic: Typewriter Effect
        function openLetter() {
            document.getElementById('envelope').classList.add('hidden');
            document.getElementById('notePaper').classList.remove('hidden');
            typeWriter();
        }

        const message = "I just wanted to tell you something... you really are special in a way that's hard to explain. There's a softness in the way you talk, a sweetness in the way you smile, and something genuine about you that just feels good to be around. You don't try to be anything extra, you're just you, and that's what makes you so lovely Par tu fir bhi budhuu h ";
        let i = 0;
        
        function typeWriter() {
            if (i < message.length) {
                document.getElementById("typedText").innerHTML += message.charAt(i);
                i++;
                setTimeout(typeWriter, 10); 
            } else {
                document.getElementById('finalBtn').classList.remove('hidden');
            }
        }
    </script>
</body>
</html>
<img src="1000342402.jpg" class="circle-img" alt="My Photo">
