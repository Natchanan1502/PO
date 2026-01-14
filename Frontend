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
    <input type="text" id="po" required><br><br>

    <label>Material Code</label><br>
    <input type="text" id="material" required><br><br>

    <button type="submit">Submit</button>
</form>

<p id="result"></p>

<script>
const scriptURL =
"https://script.google.com/macros/s/AKfycbwFGb6lf0LKol4P7qw8tFJnSpL0WNHED49EhcJdnGvOnLrewQx8DZ2k2aD0B8RWOTZy/exec";

document.getElementById("poForm").addEventListener("submit", function(e) {
    e.preventDefault();

    const data = new FormData();
    data.append("po", document.getElementById("po").value);
    data.append("material", document.getElementById("material").value);

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
    .catch(err => {
        document.getElementById("result").innerText = "Error";
        console.error(err);
    });
});
</script>

</body>
</html>

