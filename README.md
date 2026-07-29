<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Client Information Form</title>

<style>

body{
    font-family:Arial, sans-serif;
    background:#f2f2f2;
}

.container{
    width:400px;
    margin:50px auto;
    background:white;
    padding:20px;
    border-radius:10px;
    box-shadow:0 0 10px rgba(0,0,0,0.2);
}

h2{
    text-align:center;
    color:#0d6efd;
}

input,textarea{
    width:100%;
    padding:10px;
    margin-top:10px;
    margin-bottom:15px;
    border:1px solid #ccc;
    border-radius:5px;
}

button{
    width:100%;
    padding:10px;
    background:#0d6efd;
    color:white;
    border:none;
    border-radius:5px;
    cursor:pointer;
}

button:hover{
    background:#084298;
}

</style>

</head>
<body>

<div class="container">

<h2>Client Information</h2>

<input type="text" placeholder="Client Name">

<input type="text" placeholder="Phone Number">

<input type="email" placeholder="Email Address">

<textarea placeholder="Address"></textarea>

<button>Save Client</button>

</div>

</body>
</html>
