<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Responsive UI Grid</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans:ital,wght@0,100..900;1,100..900&display=swap" rel="stylesheet">

<style>
    body {
        font-family: Arial, sans-serif;
        margin: 0;
        padding: 0;
        font-family: "Noto Sans", sans-serif;
    }
    .grid {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        grid-template-rows: repeat(4, auto);
        gap: 60px;
        padding: 60px;
    }
    .grid-item {
        border: 1px solid #ccc;
        padding: 18px;
        color: #03A9EB;
    }
    .grid-body{
      text-align: center;
    }
    .btn{
      cursor: pointer;
      border: 3px solid rgb(156, 195, 240);
      border-radius: 6px;
      background-color: #6870b8;
      font-size: medium;
      padding-top: 5px;
      padding-bottom: 5px;
      padding-left: 27px;
      padding-right: 27px;
      margin-left: 10px;
      margin-right: 10px;
      color: white;
    }
    .btn:hover{
      cursor: pointer;
      background-color: #8b95ed;
    }
    .btn:active{
      background-color: #8b95ed
    }
    .btn2{
      cursor: pointer;
      border: 3px solid #9af7de;
      border-radius: 6px;
      background-color: #6fc1ab;
      font-size: medium;
      width: 40px;
      padding-top: 5px;
      padding-bottom: 5px;
      margin-left: 10px;
      margin-right: 10px;
      color: rgb(255, 255, 255);
    }
    .color-btn{
      margin-left: 10px;
      margin-right: 10px;
      cursor: pointer;
      color: #03A9EB;
      border-radius: 10px;
      border: none;
      background-color: white;
      inline-size: 40px;
    }
    @media screen and (max-width: 1170px) {
      .grid {
        grid-template-columns: repeat(1, 1fr);
        padding: 20px;
        gap: 0;
      }
      .grid-item {
        border: 1px solid #ccc;
        padding: 10px;
        color: #03A9EB;
        margin: 10px;
      }
      .btn {
        padding: 0;
        font-size: small;
        background-color: white;
        color: black;
        border: none;
      }
      .btn2{
      font-size: small;
      width: 30px;
    }
}
</style>


</head>
<body class="grid-body">
<h1 style="margin-top: 40px; color: rgb(31, 155, 227);">UI Grid with Dynamic Text Formatting Controls.</h1>
<div class="grid">
    <div class="grid-item">
        <button class="btn" onclick="toggleBold(1)"><b>Bold</b></button>
        <button class="btn" onclick="toggleItalic(1)"><i>Italic</i></button>
        <button class="btn" onclick="toggleUnderline(1)"><u>Underline</u></button>
        <input  class="btn2" type="number" id="fontSizeInput1" min="10" max="30" value="16" onchange="changeFontSize(1)">
        
    </div>
    <div class="grid-item" id="sentence1">He's not the sharpest knife in the drawer.
      <input class="color-btn" type="color" id="colorInput1" value="#03A9EB" onchange="changeColor(1)">
    </div>

    <div class="grid-item">
      <button class="btn" onclick="toggleBold(2)"><b>Bold</b></button>
        <button class="btn" onclick="toggleItalic(2)"><i>Italic</i></button>
        <button class="btn" onclick="toggleUnderline(2)"><u>Underline</u></button>
      <input class="btn2" type="number" id="fontSizeInput2" min="10" max="30" value="16" onchange="changeFontSize(2)">
    
  </div>
  <div class="grid-item" id="sentence2">The big buildinig was blazing with lights.
    <input class="color-btn" type="color" id="colorInput2" value="#03A9EB" onchange="changeColor(2)" >
  </div>

  <div class="grid-item">
    <button class="btn" onclick="toggleBold(3)"><b>Bold</b></button>
        <button class="btn" onclick="toggleItalic(3)"><i>Italic</i></button>
        <button class="btn" onclick="toggleUnderline(3)"><u>Underline</u></button>
    <input class="btn2" type="number" id="fontSizeInput3" min="10" max="30" value="16" onchange="changeFontSize(3)">
    
</div>
<div class="grid-item" id="sentence3">Now you must answer some big questions.
  <input class="color-btn" type="color" id="colorInput3" value="#03A9EB" onchange="changeColor(3)">
</div>

<div class="grid-item">
  <button class="btn" onclick="toggleBold(4)"><b>Bold</b></button>
        <button class="btn" onclick="toggleItalic(4)"><i>Italic</i></button>
        <button class="btn" onclick="toggleUnderline(4)"><u>Underline</u></button>
  <input class="btn2" type="number" id="fontSizeInput4" min="10" max="30" value="16" onchange="changeFontSize(4)">
  
</div>
<div class="grid-item" id="sentence4">Get Your Act Togather!
  <input class="color-btn" type="color" id="colorInput4" value="#03A9EB" onchange="changeColor(4)">
</div>

</div>


<script>
    function toggleBold(id) {
        var sentence = document.getElementById('sentence' + id);
        sentence.style.fontWeight = sentence.style.fontWeight === 'bold' ? 'normal' : 'bold';
    }

    function toggleItalic(id) {
        var sentence = document.getElementById('sentence' + id);
        sentence.style.fontStyle = sentence.style.fontStyle === 'italic' ? 'normal' : 'italic';
    }

    function toggleUnderline(id) {
        var sentence = document.getElementById('sentence' + id);
        sentence.style.textDecoration = sentence.style.textDecoration === 'underline' ? 'none' : 'underline';
    }

    function changeFontSize(id) {
        var sentence = document.getElementById('sentence' + id);
        var fontSize = document.getElementById('fontSizeInput' + id).value + 'px';
        sentence.style.fontSize = fontSize;
    }

    function changeColor(id) {
        var sentence = document.getElementById('sentence' + id);
        var color = document.getElementById('colorInput' + id).value;
        sentence.style.color = color;
    }
</script>

</body>
</html>
