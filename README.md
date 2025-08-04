# Creating the final HTML file for use with Netlify Drop
final_html_content = """
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TrainEasy Jet - Votre Billet</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .ticket {
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            width: 350px;
            padding: 20px;
            text-align: center;
        }
        .header {
            background-color: #005582;
            color: white;
            padding: 10px;
            border-radius: 5px;
            margin-bottom: 20px;
        }
        .ticket-info {
            text-align: left;
            margin-bottom: 20px;
        }
        .qr-code {
            background-color: #eee;
            height: 100px;
            display: flex;
            justify-content: center;
            align-items: center;
            border-radius: 5px;
            margin-bottom: 20px;
        }
        .footer {
            font-size: 12px;
            color: #666;
        }
        button {
            background-color: #005582;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }
        button:hover {
            background-color: #003366;
        }
        select {
            width: 100%;
            padding: 8px;
            margin: 5px 0 15px 0;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
    </style>
</head>
<body>
    <div class="ticket">
        <div class="header">
            <h2>TrainEasy Jet</h2>
        </div>
        <h3>Billet Électronique</h3>
        <div class="ticket-info">
            <p><strong>Nom du Passager :</strong> [Votre Nom]</p>
            <p><strong>Numéro de Train :</strong> TEJ12345</p>
            <p><strong>Date de Départ :</strong> [Date]</p>
            <p><strong>Heure de Départ :</strong> [Heure]</p>
            <p><strong>Gare de Départ :</strong> Bistrot du Jardin</p>
            <p><strong>Gare d'Arrivée :</strong>
            <select id="arrivalStation" onchange="changeArrivalStation()">
                <option value="Karaoké">Karaoké</option>
                <option value="Bistrot du Jardin">Bistrot du Jardin</option>
                <option value="Au Bureau">Au Bureau</option>
                <option value="Au Lit">Au Lit</option>
                <option value="Chez Joffray">Chez Joffray</option>
            </select></p>
            <p><strong>Numéro de Siège :</strong> <span id="seatNumber">[Numéro]</span></p>
            <p><strong>Voiture :</strong> <span id="carNumber">[Numéro]</span></p>
            <p><strong>Classe :</strong> [Classe]</p>
            <p><strong>Numéro de Billet :</strong> TEJ-[Numéro de Billet]</p>
        </div>
        <div class="qr-code">
            <p>QR Code</p>
        </div>
        <button onclick="changeNumbers()">Changer les numéros</button>
        <div class="footer">
            <p><strong>Conditions Générales :</strong></p>
            <p>Veuillez arriver au moins 30 minutes avant le départ.</p>
            <p>Présentez ce billet et une pièce d'identité valide à bord du train.</p>
            <p>Ce billet est non remboursable et non échangeable.</p>
        </div>
    </div>

    <script>
        function changeNumbers() {
            const seatNumber = Math.floor(Math.random() * 100) + 1;
            const carNumber = Math.floor(Math.random() * 20) + 1;
            document.getElementById('seatNumber').textContent = seatNumber;
            document.getElementById('carNumber').textContent = carNumber;
        }
        function changeArrivalStation() {
            const arrivalStation = document.getElementById('arrivalStation').value;
        }
    </script>
</body>
</html>
"""

# Save the final HTML content to a file
final_file_path = 'train_ticket_final.html'
with open(final_file_path, 'w') as file:
    file.write(final_html_content)

final_file_path
