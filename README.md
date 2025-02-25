# Mel-Michele
About love❤️ and future
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quiz Interactif</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f4f4f4;
            margin: 50px;
        }
        .quiz-container {
            background-color: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0px 0px 10px gray;
            width: 60%;
            margin: auto;
        }
        input {
            padding: 10px;
            margin: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        button {
            padding: 10px 15px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }
        button:hover {
            background-color: #0056b3;
        }
        #resultat {
            font-size: 18px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="quiz-container">
        <h1>Quiz Fun 🎉</h1>
        <p id="question"></p>
        <input type="text" id="reponse" placeholder="Ta réponse ici">
        <button onclick="suivant()">Valider</button>
        <p id="resultat"></p>
        <p id="progression"></p>
    </div>

    <script>
        // Liste de 10 questions différentes
        let questions = [
            "Quel est ton film préféré ?",
            "Si tu pouvais avoir un super-pouvoir, ce serait quoi ?",
            "Quel est le nom de ton premier animal de compagnie ?",
            "Quelle est la meilleure chose qui te soit arrivée cette année ?",
            "Si tu pouvais voyager dans le temps, où irais-tu ?",
            "Quel est ton plat préféré ?",
            "Si tu pouvais être un personnage de dessin animé, qui serais-tu ?",
            "Quelle chanson écoutes-tu en boucle en ce moment ?",
            "Si tu gagnais 1 million d'euros, que ferais-tu en premier ?",
            "Si tu pouvais dîner avec une célébrité, qui choisirais-tu ?"
        ];

        let index = 0; // Question actuelle

        function afficherQuestion() {
            if (index < 10) {
                document.getElementById("question").innerText = questions[index];
                document.getElementById("reponse").value = "";
                document.getElementById("resultat").innerText = "";
                document.getElementById("progression").innerText = `Question ${index + 1} / 10`;
            } else {
                document.querySelector(".quiz-container").innerHTML = "<h1>🎉 Bravo, tu as terminé le quiz !</h1>";
            }
        }

        function suivant() {
            let reponse = document.getElementById("reponse").value;
            let resultat = document.getElementById("resultat");

            if (reponse.trim() === "") {
                resultat.innerHTML = "🤔 Oops ! Tu dois entrer une réponse.";
                resultat.style.color = "red";
            } else {
                let messages = ["👍 Bonne réponse !", "🎯 Parfait !", "💡 Intéressant !", "👏 Super choix !", "🔥 Trop bien !"];
                let messageAleatoire = messages[Math.floor(Math.random() * messages.length)];
                
                resultat.innerHTML = messageAleatoire;
                resultat.style.color = "green";

                setTimeout(() => {
                    index++;
                    afficherQuestion();
                }, 1000);
            }
        }

        // Afficher la première question
        afficherQuestion();
    </script>
</body>
</html>
