<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>PO</title>
</head>
<body>

<h1>PO</h1>

<form id="poForm">
    <label>PO Number</label><br>
    <input type="number" id="po" required><br><br>

    <label>Material Code</label><br>
    <input type="number" id="material" required><br><br>

    <button type="submit">Submit</button>
</form>

<p id="result"></p>

<script>
const scriptURL =
"https://script.google.com/macros/s/AKfycbxeLtOyxOWGXjZbtc5H1fdztfDdkMNUIw1KnAWJ_n-AKqnvMJi6V53bo3U8vEpjipkQ/exec";

document.getElementById("poForm").addEventListener("submit", function(e) {
    e.preventDefault();

    const po = document.getElementById("po").value;
    const material = document.getElementById("material").value;

    // Extra safety check
    if (!/^\d+$/.test(po) || !/^\d+$/.test(material)) {
        document.getElementById("result").innerText =
            "PO and Material must be numbers only";
        return;
    }

    const data = new FormData();
    data.append("po", po);
    data.append("material", material);

    document.getElementById("result").innerText = "Saving...";

    fetch(scriptURL, {
        method: "POST",
        body: data
    })
    .then(res => res.text())
    .then(text => {
        document.getElementById("result").innerText = text;
        if (text === "success") {
            document.getElementById("poForm").reset();
        }
    })
    .catch(() => {
        document.getElementById("result").innerText = "Network error";
    });
});
</script>

</body>
</html>
