
<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <title>رسالة حب</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: 'Arial', sans-serif;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: linear-gradient(to bottom, #ff9a9e, #fad0c4);
            overflow: hidden;
            color: #fff;
        }

        #passwordBox, #message {
            background-color: rgba(0,0,0,0.6);
            padding: 30px;
            border-radius: 20px;
            text-align: center;
            z-index: 2;
            position: relative;
        }

        input[type="password"] {
            padding: 10px;
            border-radius: 10px;
            border: none;
            margin-top: 10px;
            font-size: 16px;
        }

        button {
            padding: 10px 20px;
            margin-top: 10px;
            border: none;
            border-radius: 10px;
            background-color: pink;
            color: #000;
            font-size: 16px;
            cursor: pointer;
        }

        #message {
            display: none;
            font-size: 20px;
        }

        /* قلوب ودباديب متحركة */
        .floating {
            position: absolute;
            font-size: 24px;
            animation: floatUp linear infinite;
        }

        @keyframes floatUp {
            0% {transform: translateY(0) scale(1);}
            50% {transform: translateY(-150px) scale(1.2);}
            100% {transform: translateY(-300px) scale(1);}
        }
    </style>
</head>
<body>

<div id="passwordBox">
    <h2>ادخلي كلمة المرور عشان تشوفي رسالتي 💖</h2>
    <input type="password" id="passInput" placeholder="كلمة المرور">
    <br>
    <button onclick="checkPassword()">افتح الرسالة</button>
</div>

<div id="message">
    <h1>أنا آسف يا حبيبتي و معلش نا عارف ان حصلك مشاكل بسببى بس اسف و اللهي ❤️</h1>
    <p>بحبك جدًا و الله و مقدرش اعيش من غيرك 💕💖💘</p>
</div>

<script>
    const correctPassword = "2062010"; // كلمة المرور

    function checkPassword() {
        const password = document.getElementById('passInput').value;
        if(password === correctPassword){
            document.getElementById('passwordBox').style.display = "none";
            document.getElementById('message').style.display = "block";
            createFloatingElements(); // يبدأ ظهور القلوب والدباديب
        } else {
            alert("كلمة المرور غلط 😢 حاول تاني!");
        }
    }

    function createFloatingElements() {
        const emojis = ['💖','❤️','💘','🐻','🧸']; // القلوب والدباديب
        for(let i=0; i<30; i++){
            const elem = document.createElement('div');
            elem.className = 'floating';
            elem.innerHTML = emojis[Math.floor(Math.random()*emojis.length)];
            elem.style.left = Math.random()*window.innerWidth + 'px';
            elem.style.fontSize = (20 + Math.random()*30) + 'px';
            elem.style.animationDuration = (3 + Math.random()*3) + 's';
            document.body.appendChild(elem);
            setTimeout(() => elem.remove(), 5000); // إزالة العنصر بعد الحركة
        }
        setTimeout(createFloatingElements, 500); // استمرار ظهور العناصر
    }
</script>

</body>
</html>
Add Wibsite filrs
