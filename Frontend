<!DOCTYPE html>
<html>
<head>
    <title>PO-Extra</title>
</head>
<body>

<h2>PO and Material Code Form</h2>

<form id="poForm">
    <label>PO Number:</label><br>
    <input type="text" id="po" required><br><br>

    <label>Material Code:</label><br>
    <input type="text" id="material" required><br><br>

    <button type="submit">Submit</button>
</form>

<p id="result"></p>

<script>
const scriptURL = https://script.google.com/macros/s/AKfycbw02k7bA1u7Atk2_yen1Nx1h6gBZQcJZk9Sa8P_sSU-ndzVz6SMEekQIZW8FPPu81zl/exec;

document.getElementById("poForm").addEventListener("submit", function(e) {
    e.preventDefault();

    const data = {
        po: document.getElementById("po").value,
        material: document.getElementById("material").value
    };

    fetch(scriptURL, {
        method: "POST",
        body: JSON.stringify(data)
    })
    .then(res => res.json())
    .then(() => {
        document.getElementById("result").innerText =
            "Data saved to Google Sheet successfully!";
        document.getElementById("poForm").reset();
    })
    .catch(() => {
        document.getElementById("result").innerText =
            "Error saving data";
    });
});
</script>

</body>
</html>
