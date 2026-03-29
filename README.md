<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NOTE FOR YOU</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Outfit:wght@300;600&display=swap');

        * { box-sizing: border-box; margin: 0; padding: 0; }

        body {
            margin: 0;
            font-family: 'Outfit', sans-serif;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: linear-gradient(45deg, #ff9a9e, #fad0c4, #a1c4fd, #c2e9fb);
            background-size: 400% 400%;
            animation: gradientBG 10s ease infinite;
            overflow: hidden;
            flex-direction: column;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        
        .emoji {
            position: fixed;
            bottom: -50px;
            font-size: 24px;
            user-select: none;
            z-index: 1;
            animation: floatUp linear infinite;
        }

        @keyframes floatUp {
            0% { transform: translateY(0) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-110vh) rotate(360deg); opacity: 0; }
        }

        
        .card {
            position: relative;
            z-index: 10; 
            background: rgba(255, 255, 255, 0.25);
            backdrop-filter: blur(15px);
            -webkit-backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 30px;
            padding: 40px;
            text-align: center;
            box-shadow: 0 15px 35px rgba(0,0,0,0.1);
            width: 340px;
            max-height: 80vh; /* Restricts height to make it scrollable */
            overflow-y: auto; /* Enable vertical scrolling */
        }

        h2 { color: white; margin-bottom: 20px; text-shadow: 0 2px 4px rgba(0,0,0,0.1); }

        input {
            width: 100%;
            padding: 15px;
            border-radius: 15px;
            border: none;
            margin-bottom: 20px;
            outline: none;
            background: rgba(255, 255, 255, 0.8);
            text-align: center;
            font-size: 1rem;
        }

        button {
            width: 100%;
            padding: 15px;
            border-radius: 15px;
            border: none;
            background: linear-gradient(90deg, #ff8da1, #ffacc5);
            color: white;
            font-weight: 600;
            cursor: pointer;
            transition: 0.3s;
            text-transform: uppercase;
        }

        button:hover { transform: translateY(-3px); box-shadow: 0 5px 15px rgba(255,141,161,0.4); }

        #private-content { display: none; }

    </style>
</head>
<body>

    <audio id="bgMusic" loop>
        <source src="statue.mp3" type="audio/mpeg">
    </audio>

    <div id="login-screen" class="card">
        <h2>Enter Key 🧸</h2>
        <input type="password" id="keyInput" placeholder="Password...">
        <button onclick="unlockSite()">OPEN NOTE</button>
    </div>

    <div id="private-content" class="card">
        <h2> 𝚕𝚘𝚟𝚒𝚗𝚐 𝚢𝚘𝚞 𝚏𝚛𝚘𝚖 𝚊𝚏𝚊𝚛 💞</h2>
        <p style="color: white; line-height: 1.5;"> There is something I have long kept within my heart, a truth I can no longer conceal in silence. For quite some time now, my thoughts have been quietly drawn toward you, and with each passing day, those feelings have only grown deeper and more sincere. I tried to convince myself that perhaps it was only a passing admiration, something temporary that would fade with time. Yet no matter how much I attempted to ignore it, the feeling remained, constant and undeniable.

Your presence has a quiet way of bringing light into my days. The smallest moments--our conversations, your laughter, even the way you simply exist--have left a lasting impression on me. I find myself appreciating not only the happiness you bring but also the kindness, intelligence, and sincerity that define who you are as a person. These qualities are rare, and it is impossible not to admire them.

I want to be honest with you, not because I expect anything in return, but because honesty is the only way I can give these feelings the respect they deserve. What I feel for you is genuine. It is not built upon fleeting emotions or momentary fascination, but upon sincere admiration and deep appreciation for who you truly are.

I understand that confessions like this can sometimes place unexpected weight upon someone's heart, and that is never my intention. My purpose is not to pressure you or create discomfort. Rather, I simply wish to express what has long been within me. Whatever your feelings may be, I will respect them with complete understanding.

Still, I hope that perhaps, in some quiet corner of your thoughts, you might see the sincerity behind these words. If nothing else, I hope you know that you are deeply valued and appreciated more than you may ever realize.

Thank you for being someone who unknowingly brought warmth and meaning into my life. And regardless of what the future may hold, I will always be grateful that I found the courage to tell you the truth of my heart. i hope payagan mo akong ligawan ka my love love hehehee mwuaaa iloveyouuuuuusomuchhhhh my jaera>_< </p>
        <button onclick="lockSite()" style="margin-top: 20px; background: #666;">CLOSE</button>
    </div>

    <script>
        const song = document.getElementById("bgMusic");

        
        function createEmoji() {
            const emoji = document.createElement('div');
            emoji.className = 'emoji';
            emoji.innerText = '🧸💕';
            
            
            emoji.style.left = Math.random() * 100 + 'vw';
            
            
            emoji.style.fontSize = (Math.random() * 20 + 20) + 'px';
            
            
            const duration = Math.random() * 5 + 5;
            emoji.style.animationDuration = duration + 's';
            
            
            emoji.style.opacity = Math.random() * 0.5 + 0.5;

            document.body.appendChild(emoji);

            
            setTimeout(() => {
                emoji.remove();
            }, duration * 1000);
        }

        
        setInterval(createEmoji, 500);

        function unlockSite() {
            const pass = document.getElementById("keyInput").value;
            if(pass === "WOW") {
                document.getElementById("login-screen").style.display = "none";
                document.getElementById("private-content").style.display = "block";
                song.play();
            } else {
                alert("Wrong Key! Try again 🌸");
            }
        }

        function lockSite() {
            song.pause();
            song.currentTime = 0;
            document.getElementById("keyInput").value = "";
            document.getElementById("private-content").style.display = "none";
            document.getElementById("login-screen").style.display = "block";
        }
    </script>
</body>
</html>
