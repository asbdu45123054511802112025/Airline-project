
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Airline Booking</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Airline Booking System</h1>
    </header>
    <main>
        <form id="flightSearchForm">
            <label for="departure">Departure City:</label>
            <input type="text" id="departure" placeholder="Enter departure city" required>

            <label for="destination">Destination City:</label>
            <input type="text" id="destination" placeholder="Enter destination city" required>

            <label for="date">Travel Date:</label>
            <input type="date" id="date" required>

            <button type="submit">Search Flights</button>
        </form>
        <section id="results">
            <!-- Flight results will be displayed here -->
        </section>
    </main>
    <script src="script.js"></script>
</body>
</html>


---

CSS (styles.css)

body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f4f4f9;
    color: #333;
}

header {
    background-color: #0077b6;
    color: white;
    text-align: center;
    padding: 1rem 0;
}

main {
    max-width: 800px;
    margin: 2rem auto;
    padding: 1rem;
    background: white;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

form {
    display: flex;
    flex-direction: column;
    gap: 1rem;
}

label {
    font-weight: bold;
}

input, button {
    padding: 0.8rem;
    font-size: 1rem;
    border: 1px solid #ccc;
    border-radius: 4px;
}

button {
    background-color: #0077b6;
    color: white;
    cursor: pointer;
    border: none;
}

button:hover {
    background-color: #005f8b;
}

#results {
    margin-top: 2rem;
    padding: 1rem;
    border-top: 1px solid #ccc;
}

.flight-result {
    padding: 1rem;
    border: 1px solid #ddd;
    border-radius: 4px;
    margin-bottom: 1rem;
    background-color: #f9f9f9;
}


---

JavaScript (script.js)

document.getElementById('flightSearchForm').addEventListener('submit', function (e) {
    e.preventDefault();

    // Get form values
    const departure = document.getElementById('departure').value;
    const destination = document.getElementById('destination').value;
    const date = document.getElementById('date').value;

    // Example: Simulated flight data
    const flights = [
        { airline: 'Airline A', flightNo: 'AA101', price: '$200' },
        { airline: 'Airline B', flightNo: 'BB202', price: '$250' },
        { airline: 'Airline C', flightNo: 'CC303', price: '$180' }
    ];

    // Display results
    const resultsSection = document.getElementById('results');
    resultsSection.innerHTML = `<h2>Available Flights</h2>`;

    flights.forEach(flight => {
        const flightDiv = document.createElement('div');
        flightDiv.classList.add('flight-result');
        flightDiv.innerHTML = `
            <p><strong>Airline:</strong> ${flight.airline}</p>
            <p><strong>Flight No:</strong> ${flight.flightNo}</p>
            <p><strong>Price:</strong> ${flight.price}</p>
        `;
        resultsSection.appendChild(flightDiv);
    }
    });

