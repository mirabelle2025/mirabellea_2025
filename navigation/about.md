---
layout: page
title: About Mirabelle
permalink: /about/

---

<h1> My Background </h1>



<style>
    /* Style looks pretty compact, trace grid-container and grid-item in the code */
    .grid-container {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(150px, 1fr)); /* Dynamic columns */
        gap: 10px;
    }
    .grid-item {
        text-align: center;
    }
    .grid-item img {
        width: 100%;
        height: 100px; /* Fixed height for uniformity */
        object-fit: contain; /* Ensure the image fits within the fixed height */
    }
    .grid-item p {
        margin: 5px 0; /* Add some margin for spacing */
    }
</style>

<!-- This grid_container class is for the CSS styling, the id is for JavaScript connection -->
<div class="grid-container" id="grid_container">
    <!-- content will be added here by JavaScript -->
</div>

<script>
    // 1. Make a connection to the HTML container defined in the HTML div
    var container = document.getElementById("grid_container"); // This container connects to the HTML div

    // 2. Define a JavaScript object for our http source and our data rows for the Living in the World grid
    var http_source = "https://upload.wikimedia.org/wikipedia/commons/";
    var living_in_the_world = [
        {"flag": "0/01/Flag_of_California.svg", "description": "California - Home (Moved here at 1 yrs old)"},
        {"flag": "5/5a/Flag_of_Missouri.svg", "description": "Missouri - Birthplace (Dad's side lives in Missouri)"},
        {"flag": "7/72/Flag_of_the_Republic_of_China.svg", "description": "Taiwanese - Ethnicity (Mom's side lives in Taiwan)"},
    ]; 
    
    // 3a. Consider how to update style count for size of container
    // The grid-template-columns has been defined as dynamic with auto-fill and minmax

    // 3b. Build grid items inside of our container for each row of data
    for (const location of living_in_the_world) {
        // Create a "div" with "class grid-item" for each row
        var gridItem = document.createElement("div");
        gridItem.className = "grid-item";  // This class name connects the gridItem to the CSS style elements
        // Add "img" HTML tag for the flag
        var img = document.createElement("img");
        img.src = http_source + location.flag; // concatenate the source and flag
        img.alt = location.flag + " Flag"; // add alt text for accessibility

        // Add "p" HTML tag for the description
        var description = document.createElement("p");
        description.textContent = location.description; // extract the description

        // Add "p" HTML tag for the greeting
        var greeting = document.createElement("p");
        greeting.textContent = location.greeting;  // extract the greeting

        // Append img and p HTML tags to the grid item DIV
        gridItem.appendChild(img);
        gridItem.appendChild(description);
        gridItem.appendChild(greeting);

        // Append the grid item DIV to the container DIV
        container.appendChild(gridItem);
    }
</script>

<h1> My Interests </h1>

- ⚽ I've played soccer for over 10 years (<a href="https://www.youtube.com/@mirabelle.anderson2025">Here are some highlights!!</a>)
- 👨‍👩‍👧‍👦 I have an older brother that attends UC Berkeley, and a mom and dad
- 🐩 I have a maltipoo dog named Powder and shes my bestfriend
- 🏈, 🏐, 🥎 I have played flag football, volleyball, and softball competitvely
- ➕ My favorite subject is math
- 🫡 I am the captain of my club soccer team, high school soccer team, and high school flag football team
- 🗣️ I am fluent in Madarin
- 🏂 I have been snowboarding for over 8 years (My dad was going to go pro for snowboarding)
- 👩‍🔬 I want to study engineering

### Family and Fun

The most important part of my life is my family and friends.

<img src="{{site.baseurl}}/images/notebooks/about-personal/image-1.png" alt="Soccer Team" width="400" height="300"/> 
<img src= "{{site.baseurl}}/images/notebooks/about-personal/image.png" alt="Nature" width="400" height="300"/>
<comment> -----------------------------------Soccer Team ------------------------------------------------------------------Flag Football Team--------------------------------</comment>
<img src= "{{site.baseurl}}/images/notebooks/about-personal/image-2.png" alt="Nature" width="400" height="300"/>
<img src= "{{site.baseurl}}/images/notebooks/about-personal/image-3.png" alt="Nature" width="400" height="300"/>
<comment> ------------------------------------My Friends-----------------------------------------------------------------------My Brother--------------------------------------</comment>
<img src= "{{site.baseurl}}/images/notebooks/about-personal/image-8.png" alt="Nature" width="266" height="400"/>
<img src= "{{site.baseurl}}/images/notebooks/about-personal/image-9.png" alt="Nature" width="266" height="400"/>
<img src= "{{site.baseurl}}/images/notebooks/about-personal/image-10.png" alt="Nature" width="266" height="400"/>
<comment> ---------------------------Mom---------------------------------------------------Dad-------------------------------------------------Powder--------------------------</comment>
<img src= "{{site.baseurl}}/images/notebooks/about-personal/image-4.png" alt="Sunset" width="400" height="300"/>
<img src= "{{site.baseurl}}/images/notebooks/about-personal/image-5.png" alt="Nature" width="400" height="300"/>
<comment> ---------------------------Sunsets and Beaches have my 💗-----------------------------------------------Nature brings me peace------------------------------</comment>

<body style="background-color:pink;">

