- 👋 Hi, I’m @MSANGI09
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
MSANGI09/MSANGI09 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Plagiarism Checker</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f7f7f7;
        }

        header {
            background-color: #3498db;
            color: #fff;
            text-align: center;
            padding: 1em 0;
        }

        main {
            padding: 2em;
        }

        .input-container {
            display: flex;
            flex-direction: column;
            gap: 1em;
            margin-bottom: 1em;
        }

        textarea {
            width: 100%;
            height: 100px;
            padding: 0.5em;
            border: 1px solid #ccc;
            resize: vertical;
        }

        button {
            background-color: #3498db;
            color: #fff;
            border: none;
            padding: 0.5em 1em;
            cursor: pointer;
        }

        button:hover {
            background-color: #2980b9;
        }

        #result {
            padding: 1em;
            border: 1px solid #ccc;
            background-color: #fff;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }

        footer {
            text-align: center;
            padding: 1em 0;
            background-color: #3498db;
            color: #fff;
        }

        img {
            max-width: 100%;
            height: auto;
            border-radius:100%;
            padding:0.7%;
        }
    </style>
</head>
<body>
    <header>
        <img src="juli.jpg"  alt="MSANGI JR Plagiarism Checker Logo" >
        <h3><b>MSANGI.JR😊</b></h3>
        <h1>Plagiarism Checker</h1>
    </header>
    <main>
        <div class="input-container">
            <textarea id="text1" placeholder="Enter text 1"></textarea>
            <textarea id="text2" placeholder="Enter text 2"></textarea>
            <button id="check-button">Check Plagiarism</button>
        </div>
        <div id="result"></div>
    </main>
    <footer>
        <p>&copy; 2023 Plagiarism Checker</p>
    </footer>
    <script>
        const checkButton = document.getElementById('check-button');
        const resultDiv = document.getElementById('result');

        checkButton.addEventListener('click', () => {
            const text1 = document.getElementById('text1').value.toLowerCase();
            const text2 = document.getElementById('text2').value.toLowerCase();
            const similarityScore = calculateSimilarity(text1, text2);
            displayResult(similarityScore);
        });

        function calculateSimilarity(text1, text2) {
            const words1 = text1.split(/\W+/).filter(word => word.length > 0);
            const words2 = text2.split(/\W+/).filter(word => word.length > 0);
            const commonWords = words1.filter(word => words2.includes(word));
            const similarityScore = (commonWords.length / Math.sqrt(words1.length * words2.length)) * 100;
            return similarityScore.toFixed(2);
        }

        function displayResult(similarityScore) {
            resultDiv.innerHTML = `<p>Similarity Score: ${similarityScore}%</p>`;
        }
    </script>
</body>
</html>
