<!DOCTYPE html>
<html>
<head>
    <title>Location Access</title>
</head>
<body>
    <h1>Get Device Location</h1>
    <button onclick="getLocation()">Get Location</button>
    <p id="location"></p>

    <script>
        function getLocation() {
            if (!navigator.geolocation) {
                document.getElementById("location").innerHTML = 
                    "Geolocation not supported!";
                return;
            }

            navigator.geolocation.getCurrentPosition(
                (position) => {
                    document.getElementById("location").innerHTML =
                        "Latitude: " + position.coords.latitude + "<br>" +
                        "Longitude: " + position.coords.longitude;
                },
                (error) => {
                    document.getElementById("location").innerHTML =
                        "Error: " + error.message;
                }
            );
        }
    </script>
</body>
</html>
