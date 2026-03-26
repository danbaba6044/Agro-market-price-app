<!DOCTYPE html>
<html>
<head>
    <title>Agro Market Price App</title>
    <style>
        body {
            font-family: Arial;
            text-align: center;
            background-color: #eef7ee;
        }

        h1 {
            color: green;
        }

        table {
            margin: auto;
            border-collapse: collapse;
            width: 80%;
        }

        th, td {
            border: 1px solid #ccc;
            padding: 10px;
        }

        th {
            background-color: green;
            color: white;
        }

        button {
            padding: 10px;
            background-color: green;
            color: white;
            border: none;
            margin-top: 10px;
        }
    </style>
</head>

<body>

<h1>🌱 Agro Market Price App</h1>

<p>Select Crop:</p>

<select id="crop">
    <option value="maize">Maize</option>
    <option value="rice">Rice</option>
    <option value="yam">Yam</option>
</select>

<br><br>

<button onclick="showPrices()">Check Market Prices</button>

<br><br>

<table id="priceTable">
    <tr>
        <th>Crop</th>
        <th>Price</th>
        <th>Market</th>
        <th>Location</th>
    </tr>
</table>

<script>
function showPrices() {
    let crop = document.getElementById("crop").value;

    let data = {
        maize: [
            {price: "₦45,000", market: "Wukari Market", location: "Taraba"},
            {price: "₦47,000", market: "Jalingo Market", location: "Taraba"},
            {price: "₦50,000", market: "Abuja Market", location: "FCT"}
        ],
        rice: [
            {price: "₦70,000", market: "Makurdi Market", location: "Benue"},
            {price: "₦72,000", market: "Abuja Market", location: "FCT"}
        ],
        yam: [
            {price: "₦30,000", market: "Zaki Biam Market", location: "Benue"},
            {price: "₦32,000", market: "Jalingo Market", location: "Taraba"}
        ]
    };

    let table = document.getElementById("priceTable");

    // Clear old rows
    table.innerHTML = `
        <tr>
            <th>Crop</th>
            <th>Price</th>
            <th>Market</th>
            <th>Location</th>
        </tr>
    `;

    let selectedData = data[crop];

    selectedData.forEach(item => {
        let row = `
            <tr>
                <td>${crop}</td>
                <td>${item.price}</td>
                <td>${item.market}</td>
                <td>${item.location}</td>
            </tr>
        `;
        table.innerHTML += row;
    });
}
</script>

</body>
</html>
