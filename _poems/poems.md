---
layout: poem
title: "Changrui's Peoms"
---

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Toggle Poem Language</title>
    <style>
        body {
            text-align: center; /* This will center the poem and button */
        }
        .chinese, .english {
            display: none;
        }
        img {
            width: 100%;
            max-width: 800px;
            display: block;
            margin: 20px auto;
        }
        button {
            background-color: #e0e0e0; /* Light gray background */
            border: none; /* Remove default border */
            border-radius: 5px; /* Add some rounded corners */
            padding: 5px 10px; /* Reduce padding for a smaller button */
            margin: 10px auto; /* Center the button with less margin */
            cursor: pointer; /* Hand cursor for better UX */
            font-size: 0.8em; /* Reduce font size for a less conspicuous appearance */
        }
        button:hover {
            background-color: #d0d0d0; /* Slightly darker on hover for interactivity */
        }
    </style>
    <script>
        function toggleLanguage() {
            var chinesePoem = document.querySelector('.chinese');
            var englishPoem = document.querySelector('.english');
            
            if (chinesePoem.style.display === "none") {
                chinesePoem.style.display = "block";
                englishPoem.style.display = "none";
            } else {
                chinesePoem.style.display = "none";
                englishPoem.style.display = "block";
            }
        }
    </script>
</head>
<ul>
  {% assign sorted_poems = site.poems | sort: 'ts' | reverse%}
  {% for poem in sorted_poems %}
  {% if poem.url != page.url %}
    <li><a href="{{ poem.url }}">{{ poem.title_en }}</a></li>
{% endif %}
  {% endfor %}
</ul>
</html>

