# Agro-market-price-app
A web application that helps farmers access real-time market prices for crops
index.html
<!DOCTYPE html>
<html>
<head>
    <title>Agro Market Price App</title>
</head>

<body>

<h1>🌱 Agro Market Price App</h1>

<select id="crop">
    <option value="maize">Maize</option>
    <option value="rice">Rice</option>
    <option value="yam">Yam</option>
</select>

<button onclick="getPrice()">Check Price</button>

<h2 id="result"></h2>

<script>
function getPrice() {
    let crop = document.getElementById("crop").value;
    let price = "";

    if (crop === "maize") {
        price = "₦45,000 per bag";
    } else if (crop === "rice") {
        price = "₦70,000 per bag";
    } else if (crop === "yam") {
        price = "₦30,000 per tuber";
    }

    document.getElementById("result").innerText = "Price: " + price;
}
</script>

</body>
</html>
