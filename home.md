---
layout: home
search_exclude: true
---

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Navigation Bar</title>
    <link rel="stylesheet" href="frontcasts-styling.scss">
</head>
<body>

<nav>
    <a href="https://davidl0914.github.io/frontcasts/signup">Signup</a>
    <a href="https://davidl0914.github.io/frontcasts/edit">Edit</a>
    <a href="https://davidl0914.github.io/frontcasts/data">Data</a>
    <a href="https://davidl0914.github.io/frontcasts/settings">User Settings</a>
    <a href="https://davidl0914.github.io/frontcasts/image.html">Forum</a>
    <a href="https://davidl0914.github.io/frontcasts/search.html">Search</a>
    <a href="https://davidl0914.github.io/frontcasts/image">Share</a>
    <button class = "logoutbutton" onclick="eraseCookie()">Logout</button>
</nav>

<!-- Your page content goes here -->

<script>
    function eraseCookie() {   
        document.cookie = 'jwt=; Max-Age=0; path=/; domain=' + location.hostname;
        console.log(document.cookie) 
        window.location.reload()
    }

    // Function to get the cookie value by name
    function getCookie(name) {
        const value = `; ${document.cookie}`;
        const parts = value.split(`; ${name}=`);
        if (parts.length === 2) return parts.pop().split(';').shift();
}

    // Check if the JWT cookie exists on page load
    addEventListener("load", (event) => {
        console.log(getCookie("jwt"))
        if(getCookie("jwt")){
            return
        }
        else {
            window.location.href = "https://davidl0914.github.io/frontcasts/login.html"
        }
    })

    // Retrieve and apply theme preference from local storage
    document.addEventListener('DOMContentLoaded', function() {
        const currentTheme = localStorage.getItem('theme') || 'light'; // Default to 'light' theme if no preference is found
        document.body.classList.toggle('dark-theme', currentTheme === 'dark');
    });
</script>

</body>
</html>