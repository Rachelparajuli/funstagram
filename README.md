# funstagram
/* Style for the animated background */
body {
    margin: 0;
    padding: 0;
    font-family: Arial, sans-serif;
    background-color: #f0f0f0;
    position: relative;
}

.animated-background {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(-45deg, #ff4b2b, #ff416c, #8e44ad, #3498db);
    background-size: 400% 400%;
    animation: gradient 15s ease infinite;
    z-index: -1;
}

@keyframes gradient {
    0% {
        background-position: 0% 50%;
    }
    50% {
        background-position: 100% 50%;
    }
    100% {
        background-position: 0% 50%;
    }
}

header {
    background-color: #333;
    color: white;
    padding: 10px;
    text-align: center;
}

nav ul {
    list-style-type: none;
    padding: 0;
    margin: 0;
}

nav ul li {
    display: inline;
    margin-right: 20px;
}

nav ul li a {
    color: white;
    text-decoration: none;
}

h2 {
    text-align: center;
    color: #333;
}

.photo-feed, .game-container, .video-container {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    padding: 20px;
}

.post {
    background: white;
    border: 1px solid #ddd;
    border-radius: 10px;
    margin: 20px;
    padding: 20px;
    width: 300px;
    text-align: center;
}

.post img {
    width: 100%;
    border-radius: 10px;
}

.post-details {
    margin-top: 10px;
}

.comment-box {
    width: 100%;
    padding: 10px;
    margin-top: 10px;
}

#withdraw {
    background-color: #f0f0f0;
    padding: 20px;
    text-align: center;
}

#withdraw-form {
    margin: 0 auto;
    display: inline-block;
    text-align: left;
}

#withdraw-form select, #withdraw-form input {
    display: block;
    margin: 10px 0;
    padding: 10px;
    width: 100%;
}

footer {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 20px;
    position: relative;
    bottom: 0;
    width: 100%;
}
