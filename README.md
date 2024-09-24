// src/App.js
import React from 'react';
import { Analytics } from '@vercel/analytics/react';
import './App.css'; // Ensure you have your CSS file

const App = () => {
    return (
        <div className="App">
            <div className="animated-background"></div>

            <header>
                <h1>FunStagram</h1>
                <nav>
                    <ul>
                        <li><a href="#home">Home</a></li>
                        <li><a href="#feed">Feed</a></li>
                        <li><a href="#games">Games</a></li>
                        <li><a href="#videos">YouTube</a></li>
                        <li><a href="#withdraw">Withdraw Money</a></li>
                    </ul>
                </nav>
            </header>

            {/* Photo Feed Section */}
            <section id="feed">
                <h2>Photo Feed</h2>
                <div className="photo-feed">
                    <div className="post">
                        <img src="https://via.placeholder.com/300" alt="User Photo" />
                        <div className="post-details">
                            <span className="likes">❤️ 0</span>
                            <button className="like-btn">Like</button>
                            <input type="text" className="comment-box" placeholder="Add a comment..." />
                        </div>
                    </div>
                </div>
            </section>

            {/* Game Section */}
            <section id="games">
                <h2>Play Fun Games!</h2>
                <div className="game-container">
                    <button id="play-game">Play Simple Game</button>
                    <canvas id="gameCanvas" width="300" height="300"></canvas>
                </div>
            </section>

            {/* YouTube Section */}
            <section id="videos">
                <h2>Watch YouTube Videos</h2>
                <div className="video-container">
                    <iframe width="560" height="315" src="https://www.youtube.com/embed/YOUR_VIDEO_ID" title="YouTube video player" frameBorder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowFullScreen></iframe>
                </div>
            </section>

            {/* Withdraw Section */}
            <section id="withdraw">
                <h2>Withdraw Your Earnings</h2>
                <p>Select a method to withdraw your earnings:</p>
                <form id="withdraw-form">
                    <label htmlFor="platform">Choose a platform:</label>
                    <select id="platform" name="platform">
                        <option value="airtm">Airtm</option>
                        <option value="esewa">eSewa</option>
                        <option value="khalti">Khalti</option>
                        <option value="mobile-banking">Mobile Banking</option>
                    </select>

                    <label htmlFor="amount">Enter Amount ($):</label>
                    <input type="number" id="amount" name="amount" placeholder="Enter amount" />

                    <button type="submit">Withdraw</button>
                </form>
            </section>

            <footer>
                <p>© 2024 FunStagram - Play, Watch, Earn</p>
            </footer>

            {/* Include the Analytics component */}
            <Analytics />
        </div>
    );
};

export default App;
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
document.addEventListener('DOMContentLoaded', () => {
    // Like button functionality
    const likeButtons = document.querySelectorAll('.like-btn');
    likeButtons.forEach(button => {
        button.addEventListener('click', function() {
            const likes = this.previousElementSibling;
            let likeCount = parseInt(likes.textContent.split(' ')[1]);
            likes.textContent = `❤️ ${++likeCount}`;
        });
    });

    // Simple Game Setup
    const playGameButton = document.getElementById('play-game');
    const gameCanvas = document.getElementById('gameCanvas');
    const ctx = gameCanvas.getContext('2d');

    playGameButton.addEventListener('click', () => {
        ctx.clearRect(0, 0, gameCanvas.width, gameCanvas.height);
        ctx.fillStyle = '#ff4b2b';
        ctx.fillRect(Math.random() * 250, Math.random() * 250, 50, 50);
        alert("You caught the red square! Play again!");
    });

    // Withdraw Form Handling (Mocked)
    const withdrawForm = document.getElementById('withdraw-form');
    withdrawForm.addEventListener('submit', (e) => {
        e.preventDefault();
        const platform = document.getElementById('platform').value;
        const amount = document.getElementById('amount').value;

        if (amount > 0) {
            alert(`Your request to withdraw $${amount} via ${platform} has been submitted!`);
        } else {
            alert('Please enter a valid amount.');
        }
    });
});
import './script'; // This will execute the script file

