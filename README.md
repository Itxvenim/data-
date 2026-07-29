<!DOCTYPE html>
<html>
<head>
<title>Client Information</title>
</head>
<body>

<h2>Client Information</h2>

<input type="text" id="name" placeholder="Client Name"><br><br>

<input type="text" id="phone" placeholder="Phone Number"><br><br>

<input type="email" id="email" placeholder="Email"><br><br>

<button onclick="saveClient()">Save</button>

<h3>Saved Clients</h3>

<ul id="list"></ul>

<script>

let clients = JSON.parse(localStorage.getItem("clients")) || [];

showClients();

function saveClient(){

let name = document.getElementById("name").value;
let phone = document.getElementById("phone").value;
let email = document.getElementById("email").value;

if(name=="" || phone=="" || email==""){
alert("Fill all fields");
return;
}

clients.push({
name:name,
phone:phone,
email:email
});

localStorage.setItem("clients",JSON.stringify(clients));

document.getElementById("name").value="";
document.getElementById("phone").value="";
document.getElementById("email").value="";

showClients();

}

function showClients(){

let list=document.getElementById("list");

list.innerHTML="";

clients=JSON.parse(localStorage.getItem("clients")) || [];

for(let i=0;i<clients.length;i++){

list.innerHTML += "<li><b>"+clients[i].name+"</b> | "+clients[i].phone+" | "+clients[i].email+"</li>";

}

}

</script>

</body>
</html>
