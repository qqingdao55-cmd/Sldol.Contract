[1.html](https://github.com/user-attachments/files/23878423/1.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<link rel="stylesheet" href="logo.html/logo.png.jpg">
<title>SIdol.Contract</title>

<style>
    body {
        margin: 0;
        padding: 0;
        background: #000;
        color: #fff;
        font-family: Arial, Helvetica, sans-serif;
    }

    .container {
        max-width: 900px;
        margin: 40px auto;
        background: #111;
        padding: 40px;
        border-radius: 12px;
        box-shadow: 0 0 25px rgba(255,255,255,0.1);
    }

    .logo {
        display: block;
        margin: 0 auto 40px auto;
        width: 180px;
        height: auto;
        filter: drop-shadow(0px 0px 10px rgba(255,255,255,0.4));
    }

    h1 {
        text-align: center;
        font-size: 32px;
        margin-bottom: 20px;
        letter-spacing: 1px;
    }

    .fill-section {
        margin-bottom: 30px;
        padding: 20px;
        background: #222;
        border-radius: 10px;
    }

    input {
        padding: 6px;
        border-radius: 6px;
        border: none;
        margin-top: 5px;
        width: 260px;
    }

    button {
        margin-top: 20px;
        padding: 10px 25px;
        font-size: 16px;
        background: #333;
        color: #fff;
        border: none;
        border-radius: 6px;
        cursor: pointer;
    }

    button:hover {
        background: #666;
    }

    #resultsBox {
        display: none;
        margin-top: 40px;
        background: #222;
        padding: 20px;
        border-radius: 10px;
        white-space: pre-wrap;
    }

    #copyBtn {
        margin-top: 15px;
        background: #555;
    }
</style>
</head>

<body>

<div class="container">

    <!-- FIXED LOGO PATH -->
    <img src="logo.html/logo.png.jpg" alt="Company Logo" class="logo">

    <h1>Employment Contract</h1>

    <!-- Form -->
    <div class="fill-section">

        <label><b>Employee (Party B) Name:</b></label><br>
        <input id="empName" type="text" placeholder="Enter employee name"><br><br>

        <label><b>Employee Position:</b></label><br>
        <input id="empPosition" type="text" placeholder="Enter employee position"><br><br>

        <label><b>Employee Salary (USD):</b></label><br>
        <input id="empSalary" type="text" placeholder="Enter salary"><br><br>

        <label><b>Employer Signature Date:</b></label><br>
        <input id="empDateA" type="date"><br><br>

        <label><b>Employee Signature Date:</b></label><br>
        <input id="empDateB" type="date"><br>

        <button onclick="fillContract()">Fill Into Contract</button>
    </div>

    <p><b>Employer (Party A):</b> Schroder Quantitative Technology Co., Ltd.</p>
    <p><b>Employee (Party B):</b> <span id="outName">________________________________________</span></p>

    <p><b>Position:</b> <span id="outPosition">________________________________________</span></p>
    <p><b>Salary:</b> <span id="outSalary">__________________</span></p>

    <h2>1. Job Responsibilities</h2>
    <ol>
        <li>Promote company products and services.</li>
        <li>Invite and attract new users or clients.</li>
        <li>Participate in marketing campaigns.</li>
        <li>Provide timely updates and reports.</li>
        <li>Follow company guidelines and policies.</li>
    </ol>

    <h2>2. Working Hours and Attendance</h2>
    <ol>
        <li>Follow company working hour standards.</li>
        <li>Ensure attendance and task completion.</li>
        <li>Adjustments allowed by mutual agreement.</li>
    </ol>

    <h2>3. Compensation</h2>
    <ol>
        <li>Monthly Salary: USD <span id="outSalary2">_____________</span></li>
        <li>Paid monthly to Party B's bank account.</li>
        <li>Bonuses or commissions based on company policy.</li>
    </ol>

    <div class="signature-section">
        <p><b>Employer (Party A) Signature:</b> ____________________________</p>
        <p>Date: <span id="outDateA">____ / ____ / ______</span></p>

        <p><b>Employee (Party B) Signature:</b> <span id="outSigName">______________________________</span></p>
        <p>Date: <span id="outDateB">____ / ____ / ______</span></p>
    </div>

    <!-- Results -->
    <div id="resultsBox"></div>
    <button id="copyBtn" style="display:none;" onclick="copyResults()">Copy Completed Contract</button>

</div>

<script>
function fillContract() {
    const name = document.getElementById("empName").value;
    const position = document.getElementById("empPosition").value;
    const salary = document.getElementById("empSalary").value;
    const dateA = document.getElementById("empDateA").value;
    const dateB = document.getElementById("empDateB").value;

    // Insert into contract
    document.getElementById("outName").innerText = name || "________________________________________";
    document.getElementById("outSigName").innerText = name || "______________________________";
    document.getElementById("outPosition").innerText = position || "________________________________________";
    document.getElementById("outSalary").innerText = salary || "__________________";
    document.getElementById("outSalary2").innerText = salary || "_____________";
    document.getElementById("outDateA").innerText = dateA || "____ / ____ / ______";
    document.getElementById("outDateB").innerText = dateB || "____ / ____ / ______";

    // Results box
    let filledText = 
`Employment Contract

Employee Name: ${name}
Position: ${position}
Salary: USD ${salary}

Employer Signature Date: ${dateA}
Employee Signature Date: ${dateB}`;

    document.getElementById("resultsBox").innerText = filledText;
    document.getElementById("resultsBox").style.display = "block";
    document.getElementById("copyBtn").style.display = "inline-block";

    // WhatsApp message
    let message =
        "Contract Filled:\n" +
        "Name: " + name + "\n" +
        "Position: " + position + "\n" +
        "Salary: USD " + salary + "\n" +
        "Employer Date: " + dateA + "\n" +
        "Employee Date: " + dateB;

    let waURL = "https://wa.me/447518001664?text=" + encodeURIComponent(message);
    window.open(waURL, "_blank");
}

function copyResults() {
    navigator.clipboard.writeText(document.getElementById("resultsBox").innerText);
    alert("Contract copied!");
}
</script>

</body>
</html>
