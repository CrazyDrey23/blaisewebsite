<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Modern Login Form</title>

<link rel="stylesheet"
href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">

<style>

@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600&display=swap');

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:'Poppins',sans-serif;
}

body{
    height:100vh;
    overflow:hidden;
    display:flex;
    justify-content:center;
    align-items:center;
    background:linear-gradient(to bottom,#0f172a,#020617);
    color:white;
}

/* ===== Stars Background ===== */

.stars{
    position:absolute;
    width:100%;
    height:100%;
    overflow:hidden;
    z-index:-1;
}

.stars span{
    position:absolute;
    width:2px;
    height:2px;
    background:white;
    border-radius:50%;
    animation:animate 10s linear infinite;
}

@keyframes animate{
    0%{
        transform:translateY(0px);
        opacity:1;
    }
    100%{
        transform:translateY(-1000px);
        opacity:0;
    }
}

/* ===== Container ===== */

.container{
    width:420px;
    perspective:1000px;
}

.card{
    position:relative;
    width:100%;
    min-height:550px;
    transform-style:preserve-3d;
    transition:0.8s;
}

#toggle:checked ~ .container .card{
    transform:rotateY(180deg);
}

/* ===== Front & Back ===== */

.front,
.back{
    position:absolute;
    width:100%;
    height:100%;
    padding:40px;
    border-radius:20px;

    background:rgba(255,255,255,0.08);
    backdrop-filter:blur(12px);

    border:1px solid rgba(255,255,255,0.1);

    box-shadow:0 8px 32px rgba(0,0,0,0.3);

    backface-visibility:hidden;
}

.back{
    transform:rotateY(180deg);
}

/* ===== Title ===== */

.title{
    text-align:center;
    margin-bottom:30px;
}

.title h2{
    font-size:32px;
    margin-bottom:10px;
}

.title p{
    color:#cbd5e1;
    font-size:14px;
}

/* ===== Input ===== */

.input-box{
    position:relative;
    margin-bottom:20px;
}

.input-box input{
    width:100%;
    padding:14px 45px;
    border:none;
    outline:none;
    border-radius:12px;
    background:rgba(255,255,255,0.08);
    color:white;
    font-size:15px;
}

.input-box i{
    position:absolute;
    top:50%;
    left:15px;
    transform:translateY(-50%);
    color:#94a3b8;
}

input::placeholder{
    color:#cbd5e1;
}

/* ===== Button ===== */

.btn{
    width:100%;
    padding:14px;
    border:none;
    border-radius:12px;
    background:#38bdf8;
    color:white;
    font-size:16px;
    font-weight:600;
    cursor:pointer;
    transition:0.3s;
}

.btn:hover{
    background:#0ea5e9;
    transform:translateY(-2px);
}

/* ===== Switch ===== */

.switch{
    margin-top:25px;
    text-align:center;
    font-size:14px;
}

.switch label{
    color:#38bdf8;
    cursor:pointer;
    font-weight:600;
}

/* Hide Checkbox */

#toggle{
    display:none;
}

</style>
</head>
<body>

<!-- Stars -->
<div class="stars">
    <span style="left:10%; top:90%; animation-duration:8s;"></span>
    <span style="left:20%; top:80%; animation-duration:12s;"></span>
    <span style="left:35%; top:95%; animation-duration:9s;"></span>
    <span style="left:50%; top:70%; animation-duration:14s;"></span>
    <span style="left:65%; top:85%; animation-duration:10s;"></span>
    <span style="left:80%; top:75%; animation-duration:13s;"></span>
    <span style="left:90%; top:92%; animation-duration:11s;"></span>
</div>

<input type="checkbox" id="toggle">

<div class="container">
<div class="card">

    <!-- LOGIN -->
    <div class="front">

        <div class="title">
            <h2>Welcome Back</h2>
            <p>Login to continue</p>
        </div>

        <div class="input-box">
            <i class="fa-solid fa-user"></i>
            <input type="text" id="user" placeholder="Username">
        </div>

        <div class="input-box">
            <i class="fa-solid fa-lock"></i>
            <input type="password" id="pass" placeholder="Password">
        </div>

        <button class="btn" onclick="login()">Login</button>

        <div class="switch">
            Don't have an account?
            <label for="toggle">Sign Up</label>
        </div>

    </div>

    <!-- SIGNUP -->
    <div class="back">

        <div class="title">
            <h2>Create Account</h2>
            <p>Register new account</p>
        </div>

        <div class="input-box">
            <i class="fa-solid fa-user"></i>
            <input type="text" placeholder="Full Name">
        </div>

        <div class="input-box">
            <i class="fa-solid fa-phone"></i>
            <input type="text" placeholder="Phone Number">
        </div>

        <div class="input-box">
            <i class="fa-solid fa-envelope"></i>
            <input type="email" placeholder="Email">
        </div>

        <div class="input-box">
            <i class="fa-solid fa-lock"></i>
            <input type="password" placeholder="Password">
        </div>

        <button class="btn">Register</button>

        <div class="switch">
            Already have an account?
            <label for="toggle">Login</label>
        </div>

    </div>

</div>
</div>

<script>

function login(){

    let username = document.getElementById("user").value;
    let password = document.getElementById("pass").value;

    if(username === "blaise" && password === "admin01"){
        alert("Login Successful!");

        // redirect to another page
        window.location.href = "Task2.html";
    }
    else{
        alert("Invalid Username or Password");
    }
}

</script>

</body>
</html>
