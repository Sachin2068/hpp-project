document.getElementById("prediction-form").addEventListener("submit", async function (event) {
    event.preventDefault();

    const area = document.getElementById("area").value;
    const bedrooms = document.getElementById("bedrooms").value;
    const bathrooms = document.getElementById("bathrooms").value;

    const response = await fetch("/predict", {
        method: "POST",
        headers: {
            "Content-Type": "application/json"
        },
        body: JSON.stringify({
            area: parseFloat(area),
            bedrooms: parseFloat(bedrooms),
            bathrooms: parseFloat(bathrooms)
        })
    });

    const data = await response.json();
    document.getElementById("result").textContent = `Predicted Price: $${data.price.toFixed(2)}`;
});
