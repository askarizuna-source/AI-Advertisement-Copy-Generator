# AI-Advertisement-Copy-Generator
app
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>AI Story Generator</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="container">
    <h1>AI Story Generator</h1>

    <!-- User Inputs -->
    <div class="input-section">
      <input type="text" id="storyTitle" placeholder="Story Title (Optional)">
      <input type="text" id="mainCharacter" placeholder="Main Character Name">
      <input type="text" id="setting" placeholder="Setting / Place">
      <select id="genre">
        <option value="Adventure">Adventure</option>
        <option value="Fantasy">Fantasy</option>
        <option value="Mystery">Mystery</option>
        <option value="Science Fiction">Science Fiction</option>
        <option value="Romance">Romance</option>
        <option value="Horror">Horror</option>
        <option value="Moral">Moral / Islamic Story</option>
      </select>
      <select id="tone">
        <option value="Happy">Happy</option>
        <option value="Emotional">Emotional</option>
        <option value="Dark">Dark</option>
        <option value="Inspirational">Inspirational</option>
        <option value="Funny">Funny</option>
      </select>
      <select id="length">
        <option value="Short">Short (150–200 words)</option>
        <option value="Medium">Medium (300–400 words)</option>
        <option value="Long">Long (500–600 words)</option>
      </select>
      <button id="generateBtn">Generate Story</button>
      <button id="clearBtn">Clear</button>
    </div>

    <!-- Output Section -->
    <div class="output-section">
      <h2>Generated Story:</h2>
      <div id="storyOutput"></div>
    </div>
  </div>

  <script src="script.js"></script>
</body>
</html>
body {
  font-family: Arial, sans-serif;
  background-color: #f4f4f4;
  margin: 0;
  padding: 20px;
}

.container {
  max-width: 700px;
  margin: auto;
  background: #fff;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0,0,0,0.1);
}

h1 {
  text-align: center;
}

.input-section {
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin-bottom: 20px;
}

.input-section input, .input-section select, .input-section button {
  padding: 10px;
  font-size: 16px;
}

#generateBtn, #clearBtn {
  cursor: pointer;
  background-color: #6c63ff;
  color: #fff;
  border: none;
  border-radius: 5px;
}

#generateBtn:hover, #clearBtn:hover {
  background-color: #574fd6;
}

.output-section {
  background: #eee;
  padding: 15px;
  border-radius: 5px;
}

#storyOutput {
  white-space: pre-line;
}
document.getElementById('generateBtn').addEventListener('click', generateStory);
document.getElementById('clearBtn').addEventListener('click', clearStory);

function generateStory() {
  const title = document.getElementById('storyTitle').value || "Untitled Story";
  const character = document.getElementById('mainCharacter').value || "Alex";
  const setting = document.getElementById('setting').value || "a mysterious place";
  const genre = document.getElementById('genre').value;
  const tone = document.getElementById('tone').value;
  const length = document.getElementById('length').value;

  // Simulated story generation
  let story = `Title: ${title}\n\n`;
  story += `Once upon a time, ${character} was in ${setting}. `;
  story += `This is a ${genre.toLowerCase()} story with a ${tone.toLowerCase()} tone. `;
  
  if(length === "Short") story += "It was a short and engaging adventure that kept everyone excited.";
  else if(length === "Medium") story += "The story developed slowly, with twists and emotional moments, keeping readers engaged.";
  else story += "It was a long and detailed story, with rich scenes, character development, and multiple twists.";

  document.getElementById('storyOutput').innerText = story;
}

function clearStory() {
  document.getElementById('storyOutput').innerText = "";
  document.getElementById('storyTitle').value = "";
  document.getElementById('mainCharacter').value = "";
  document.getElementById('setting').value = "";
}
