<!DOCTYPE html>
<html>
<head>
  <title>Redirigiendo</title>
  <script>
    function redirectToNgrok() {
      var xhr = new XMLHttpRequest();
      xhr.open('GET', 'https://api.ngrok.com/endpoints', true);
      xhr.setRequestHeader('Authorization', 'Bearer {API_KEY}');
      xhr.setRequestHeader('Ngrok-Version', '2');
      xhr.onreadystatechange = function() {
        if (xhr.readyState === 4 && xhr.status === 200) {
          window.location.href = xhr.responseURL;
        }
      };
      xhr.send();
    }

    window.onload = function() {
      redirectToNgrok();
    };
  </script>
</head>
<body>
  <h1>Redirigiendo...</h1>
</body>
</html>
