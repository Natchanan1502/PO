<!DOCTYPE html>
<html>
<body>

<button onclick="send()">SEND TEST</button>

<script>
function send() {
  const data = new FormData();
  data.append("po", "TEST_PO");
  data.append("material", "TEST_MATERIAL");

  fetch("https://script.google.com/macros/s/AKfycbwFGb6lf0LKol4P7qw8tFJnSpL0WNHED49EhcJdnGvOnLrewQx8DZ2k2aD0B8RWOTZy/exec", {
    method: "POST",
    body: data
  })
  .then(r => r.text())
  .then(t => alert(t))
  .catch(e => alert("ERROR"));
}
</script>

</body>
</html>
