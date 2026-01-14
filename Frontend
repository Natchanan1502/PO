<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
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
/* Google Apps Script Web App URL */
const scriptURL =
"https://script.google.com/macros/s/AKfycbwFGb6lf0LKol4P7qw8tFJnSpL0WNHED49EhcJdnGvOnLrewQx8DZ2k2aD0B8RWOTZy/exec";

document.getElementById("poForm").addEventListener("submit", function(e) {
    e.preventDefault();

    const formData = new FormData();
    formData.append("po", document.getElementById("po").value);
    formData.append("material", document.getElementById("material").value);

    document.getElementById("result").innerText = "⏳ Saving...";

    fetch(scriptURL, {
        method: "POST",
        body: formData
    })
    .then(res => res.t
