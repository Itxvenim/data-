<!DOCTYPE html>
<html lang="en">

<head>

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Client Information System</title>

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Arial, sans-serif;
}

body{

background:#f2f5f9;
padding:40px;

}

.container{

width:90%;
max-width:900px;
margin:auto;
background:white;
padding:30px;
border-radius:10px;
box-shadow:0 0 15px rgba(0,0,0,.2);

}

h1{

text-align:center;
margin-bottom:30px;
color:#0d6efd;

}

label{

display:block;
margin-top:15px;
font-weight:bold;

}

input,
textarea{

width:100%;
padding:12px;
margin-top:5px;
border:1px solid #ccc;
border-radius:6px;
font-size:15px;

}

textarea{

height:90px;
resize:none;

}

button{

width:100%;
padding:14px;
margin-top:20px;
background:#0d6efd;
color:white;
border:none;
border-radius:6px;
font-size:16px;
cursor:pointer;

}

button:hover{

background:#084298;

}

table{

width:100%;
margin-top:30px;
border-collapse:collapse;

}

table th{

background:#0d6efd;
color:white;
padding:12px;

}

table td{

padding:10px;
border:1px solid #ddd;
text-align:center;

}

table tr:nth-child(even){

background:#f8f8f8;

}

</style>

</head>

<body>

<div class="container">

<h1>Client Information System</h1>

<label>Client Name</label>
<input type="text" id="name" placeholder="Enter Client Name">

<label>Phone Number</label>
<input type="text" id="phone" placeholder="Enter Phone Number">

<label>Email</label>
<input type="email" id="email" placeholder="Enter Email">

<label>Address</label>
<textarea id="address" placeholder="Enter Address"></textarea>

<button onclick="saveClient()">
Save Client
</button>

<h2 style="margin-top:40px;">Saved Clients</h2>

<table>

<thead>

<tr>

<th>#</th>
<th>Name</th>
<th>Phone</th>
<th>Email</th>
<th>Address</th>

</tr>

</thead>

<tbody id="clientTable">
