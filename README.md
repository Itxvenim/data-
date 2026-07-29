<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Client Information System</title>

    <!-- CSS -->
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="container">

        <h1>Client Information System</h1>

        <div class="form-box">

            <label>Client Name</label>
            <input type="text" id="name" placeholder="Enter Client Name">

            <label>Phone Number</label>
            <input type="text" id="phone" placeholder="Enter Phone Number">

            <label>Email Address</label>
            <input type="email" id="email" placeholder="Enter Email">

            <label>Address</label>
            <textarea id="address" placeholder="Enter Address"></textarea>

            <button onclick="saveClient()">
                Save Client
            </button>

        </div>

        <hr>

        <h2>Saved Clients</h2>

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

            </tbody>

        </table>

    </div>

    <script src="script.js"></script>

</body>
</html>/* Reset */

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial, Helvetica, sans-serif;
}

/* Body */

body{
    background:#f4f7fb;
    padding:40px;
}

/* Main Container */

.container{
    max-width:900px;
    margin:auto;
    background:#ffffff;
    padding:30px;
    border-radius:10px;
    box-shadow:0 5px 15px rgba(0,0,0,0.15);
}

/* Heading */

h1{
    text-align:center;
    color:#0d6efd;
    margin-bottom:25px;
}

h2{
    margin-top:20px;
    color:#333;
}

/* Form */

.form-box{
    display:flex;
    flex-direction:column;
}

label{
    margin-top:12px;
    margin-bottom:6px;
    font-weight:bold;
    color:#444;
}

input,
textarea{
    width:100%;
    padding:12px;
    border:1px solid #ccc;
    border-radius:6px;
    outline:none;
    font-size:15px;
}

input:focus,
textarea:focus{
    border-color:#0d6efd;
}

textarea{
    resize:vertical;
    min-height:90px;
}

/* Button */

button{
    margin-top:20px;
    padding:12px;
    background:#0d6efd;
    color:white;
    border:none;
    border-radius:6px;
    cursor:pointer;
    font-size:16px;
    transition:.3s;
}

button:hover{
    background:#084fc7;
}

/* Line */

hr{
    margin:30px 0;
}

/* Table */

table{
    width:100%;
    border-collapse:collapse;
    margin-top:15px;
}

table th{
    background:#0d6efd;
    color:white;
    padding:12px;
}

table td{
    padding:12px;
    border:1px solid #ddd;
    text-align:center;
}

table tr:nth-child(even){
    background:#f2f2f2;
}

table tr:hover{
    background:#e8f0ff;
}

/* Mobile */

@media(max-width:768px){

    body{
        padding:15px;
    }

    .container{
        padding:20px;
    }

    table{
        font-size:13px;
    }

    input,
    textarea,
    button{
        font-size:14px;
    }

}// Load saved clients when page opens
window.onload = function () {
    displayClients();
};

// Save Client
function saveClient() {

    let name = document.getElementById("name").value.trim();
    let phone = document.getElementById("phone").value.trim();
    let email = document.getElementById("email").value.trim();
    let address = document.getElementById("address").value.trim();

    // Validation
    if (name === "" || phone === "" || email === "" || address === "") {
        alert("Please fill all fields.");
        return;
    }

    // Client Object
    let client = {
        name: name,
        phone: phone,
        email: email,
        address: address
    };

    // Get Existing Data
    let clients = JSON.parse(localStorage.getItem("clients")) || [];

    // Add New Client
    clients.push(client);

    // Save Again
    localStorage.setItem("clients", JSON.stringify(clients));

    // Clear Form
    document.getElementById("name").value = "";
    document.getElementById("phone").value = "";
    document.getElementById("email").value = "";
    document.getElementById("address").value = "";

    // Refresh Table
    displayClients();

    alert("Client Saved Successfully!");
}

// Display Clients
function displayClients() {

    let clients = JSON.parse(localStorage.getItem("clients")) || [];

    let table = document.getElementById("clientTable");

    table.innerHTML = "";

    for (let i = 0; i < clients.length; i++) {

        table.innerHTML += `
            <tr>
                <td>${i + 1}</td>
                <td>${clients[i].name}</td>
                <td>${clients[i].phone}</td>
                <td>${clients[i].email}</td>
                <td>${clients[i].address}</td>
            </tr>
        `;
    }

}
