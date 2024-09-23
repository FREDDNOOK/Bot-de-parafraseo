# Bot-de-parafraseo
Este bot podrá parafrasear cualquier texto con un lenguaje más humano para evitar el plagio 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Text Paraphraser</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
    }
    textarea, button {
      width: 100%;
      padding: 10px;
      font-size: 16px;
      box-sizing: border-box;
      margin-bottom: 10px;
    }
    #paraphrased-text {
      white-space: pre-wrap;
    }
  </style>
</head>
<body>
  <h1>Text Paraphraser</h1>
  <p>Enter the text you want to paraphrase:</p>
  <textarea id="input-text" rows="5"></textarea>
  <button onclick="paraphraseText()">Paraphrase</button>
  <h2>Paraphrased Text:</h2>
  <div id="paraphrased-text"></div>

  <script>
    function paraphraseText() {
      const inputText = document.getElementById('input-text').value;
      const paraphrasedText = generateParaphrase(inputText);
      document.getElementById('paraphrased-text').textContent = paraphrasedText;
    }

    function generateParaphrase(text) {
      // Implement your paraphrasing logic here
      // This is a basic example, you can make it more sophisticated
      const words = text.split(' ');
      let paraphrased = '';
      for (let i = 0; i < words.length; i++) {
        if (Math.random() < 0.5) {
          paraphrased += words[i] + ' ';
        } else {
          // Replace the word with a random synonym
          const synonyms = ['replace', 'reformulate', 'restate', 'rephrase', 'reword'];
          paraphrased += synonyms[Math.floor(Math.random() * synonyms.length)] + ' ';
        }
      }
      return paraphrased.trim();
    }
  </script>
</body>
</html>
