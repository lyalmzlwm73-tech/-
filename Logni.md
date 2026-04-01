<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<title>تسجيل الدخول - بطاقة الإنترنت</title>
<style>
    /* الخلفية */
    body {
        font-family: 'Arial', sans-serif;
        margin: 0;
        padding: 0;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        background: url('https://images.unsplash.com/photo-1557682250-90d0f8f6b2f4?auto=format&fit=crop&w=1350&q=80') no-repeat center center fixed;
        background-size: cover;
        direction: rtl;
    }

    /* صندوق تسجيل الدخول */
    .login-box {
        background: rgba(255,255,255,0.95);
        width: 400px;
        padding: 40px;
        border-radius: 20px;
        box-shadow: 0 15px 25px rgba(0,0,0,0.4);
        text-align: center;
    }

    .login-box img {
        width: 80px;
        margin-bottom: 20px;
    }

    h2 {
        color: #333;
        margin-bottom: 30px;
    }

    input[type="text"], input[type="password"] {
        width: 90%;
        padding: 15px;
        margin: 10px 0;
        border: 1px solid #ccc;
        border-radius: 5px;
        font-size: 16px;
        outline: none;
        padding-left: 40px;
        background-repeat: no-repeat;
        background-position: 10px center;
        transition: 0.3s;
    }

    input[type="text"] { background-image: url('https://img.icons8.com/ios-filled/50/000000/user.png'); }
    input[type="password"] { background-image: url('https://img.icons8.com/ios-filled/50/000000/lock-2.png'); }

    input:focus { border-color: #007BFF; }

    button {
        width: 95%;
        padding: 15px;
        margin-top: 20px;
        border: none;
        border-radius: 10px;
        background: #007BFF;
        color: white;
        font-size: 18px;
        cursor: pointer;
        transition: 0.3s;
    }

    button:hover {
        background: #00f2fe;
        color: #333;
        transform: scale(1.05);
    }

    .message {
        margin-top: 20px;
        font-weight: bold;
        font-size: 16px;
    }

</style>
</head>
<body>

<div class="login-box">
    <img src="https://img.icons8.com/ios-filled/100/007BFF/download.png" alt="Logo">
    <h2>تسجيل الدخول - بطاقة الإنترنت</h2>

    <input type="text" id="username" placeholder="اسم المستخدم">
    <input type="password" id="password" placeholder="كلمة المرور">

    <button onclick="login()">دخول</button>
    <div class="message" id="message"></div>
</div>

<script>
function login() {
    const username = document.getElementById("username").value;
    const password = document.getElementById("password").value;
    const message = document.getElementById("message");

    const accounts = {
        "user1": { password: "1234", expired: false },
        "user2": { password: "5678", expired: true }
    };

    if(accounts[username]) {
        if(accounts[username].password === password) {
            if(accounts[username].expired) {
                message.style.color = "orange";
                message.textContent = "الحساب منتهي الصلاحية ⏳";
            } else {
                message.style.color = "green";
                message.textContent = "تم تسجيل الدخول بنجاح ✅";
            }
        } else {
            message.style.color = "red";
            message.textContent = "كلمة المرور غير صحيحة ❌";
        }
    } else {
        message.style.color = "red";
        message.textContent = "اسم المستخدم غير موجود ❌";
    }
}
</script>

</body>
</html>
