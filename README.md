# Sldol.Contract[1.html](https://github.com/user-attachments/files/23878133/1.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Employment Contract</title>
<link rel="shortcut icon" href="c:\Users\Administrator\Downloads\2\Picture\ok.html.jpg" type="image/x-icon">

<style>
    body {
        margin: 0;
        padding: 0;
        background: #000;
        color: #fff;
        font-family: Arial, Helvetica, sans-serif;
        line-height: 1.6;
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

    h2 {
        margin-top: 30px;
        color: #ccc;
        border-bottom: 1px solid #444;
        padding-bottom: 5px;
    }

    .signature-section {
        margin-top: 40px;
        padding-top: 20px;
        border-top: 1px solid #444;
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

    <img src="c:\Users\Administrator\Downloads\2\Picture\ok.html.jpg" alt="Company Logo" class="logo">

    <h1>Employment Contract</h1>

    <!-- Fill fields -->
    <div class="fill-section">
        <label><b>Employee (Party B) Name:</b></label><br>
        <input id="empName" type="text" placeholder="Enter employee name"><br><br>

        <label><b>Employee Position:</b></label><br>
        <input id="empPosition" type="text" placeholder="Enter employee position"><br><br>

        <label><b>Employee Monthly Salary (USD):</b></label><br>
        <input id="empSalary" type="text" placeholder="Enter monthly salary"><br><br>

        <label><b>Employer Signature Date:</b></label><br>
        <input id="empDateA" type="date"><br><br>

        <label><b>Employee Signature Date:</b></label><br>
        <input id="empDateB" type="date"><br>


        <button onclick="fillContract()">Fill Into Contract</button>
    </div>

    <p><b>Employer (Party A):</b> Schroder Quantitative Technology Co., Ltd.</p>
    <p><b>Employee (Party B):</b> <span id="outName">________________________________________</span></p>

    <p><b>Position:</b> <span id="outPosition">____________________________________________</span></p>
    <p><b>Contract Term:</b> <span id="outPosition"> From ___ ____ _____to____ ______ _____ </span></p>

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
        <li>Monthly Salary: USD <span id="outSalary">___________</span></li>
        <li>Paid monthly to Party B's bank account.</li>
        <li>Bonuses or commissions based on company policy.</li>
    </ol>

    <h2>4. Conduct and Professional Standards</h2>
    <ol>
        <li>Act professionally toward others.</li>
        <li>Follow company communication rules.</li>
        <li>Avoid actions harming company reputation.</li>
        <li>Use only approved promotional materials.</li>
    </ol>

    <h2>5. Use of Company Resources</h2>
    <ol>
        <li>Use provided equipment responsibly.</li>
        <li>Do not misuse company property.</li>
        <li>Return all materials at contract end.</li>
    </ol>

    <h2>6. Contract Termination</h2>
    <p>Party A may terminate contract if Party B:</p>
    <ol>
        <li>Fails or neglects duties.</li>
        <li>Violates company rules.</li>
        <li>Engages in misconduct.</li>
        <li>Other legal reasons apply.</li>
    </ol>

    <h2>7. Dispute Resolution</h2>
    <p>Disputes resolved by negotiation or local law.</p>

    <h2>8. Other Provisions</h2>
    <ol>
        <li>Effective upon both signatures.</li>
        <li>Changes require written agreement.</li>
        <li>Other matters supplemented as needed.</li>
    </ol>

    <div class="signature-section">
        <p><b>Employer (Party A) Signature:</b> ____________________________</p>
        <p>Date: <span id="outDateA">____ / ____ / ______</span></p>

        <p><b>Employee (Party B) Signature:</b> <span id="outSigName">______________________________</span></p>
        <p>Date: <span id="outDateB">____ / ____ / ______</span></p>
    </div>

    <!-- RESULTS BOX -->
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

    // Fill contract lines
    document.getElementById("outName").innerText = name || "________________________________________";
    document.getElementById("outSigName").innerText = name || "______________________________";
    document.getElementById("outPosition").innerText = position || "____________________________________________";
    document.getElementById("outSalary").innerText = salary || "___________";

    document.getElementById("outDateA").innerText = dateA || "____ / ____ / ______";
    document.getElementById("outDateB").innerText = dateB || "____ / ____ / ______";

    // Build copyable text
    let filledText =
`Employment Contract

Employee Name: ${name || "N/A"}
Position: ${position || "N/A"}
Salary: USD ${salary || "N/A"}

Employer Signature Date: ${dateA || "N/A"}
Employee Signature Date: ${dateB || "N/A"}`;

    document.getElementById("resultsBox").style.display = "block";
    document.getElementById("resultsBox").innerText = filledText;

    document.getElementById("copyBtn").style.display = "inline-block";

    // WhatsApp Notification
    let message =
        "Contract form filled:\n\n" +
        "Name: " + (name || "Not entered") + "\n" +
        "Position: " + (position || "Not entered") + "\n" +
        "Salary: USD " + (salary || "Not entered") + "\n" +
        "Employer Date: " + (dateA || "Not entered") + "\n" +
        "Employee Date: " + (dateB || "Not entered");

    let url = "https://wa.me/447518001664?text=" + encodeURIComponent(message);
    window.open(url, "_blank");
}

function copyResults() {
    const text = document.getElementById("resultsBox").innerText;
    navigator.clipboard.writeText(text);
    alert("Completed contract copied!");
}
</script>

</body>
</html>
