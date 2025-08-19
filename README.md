[index.html](https://github.com/user-attachments/files/21873059/index.html)
<!DOCTYPE html>
<html lang="en" >
<head>
  <meta charset="UTF-8">
  <title>CodePen - A Pen by Dustin Poelker</title>
  <link rel="stylesheet" href="./style.css">

</head>
<body>
<!-- partial:index.partial.html -->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>THEE WINDOWS 
  </title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <div class="bg-image"></div>

  <header>
    <h1 class="band-name">THEE WINDOWS</h1>
    <h2 class="album-title">T 0 M A T A T 0 M A T 0</h2>
  </header>

  <section>
    <div class="countdown" id="countdown">LOADING...</div>
  </section>

  <section>
    <form action="#" class="email-form" id="email-form">
      <input type="email" name="email" placeholder="YOUR EMAIL" required />
      <button type="submit">JOIN</button>
    </form>
    <p id="form-message"></p>
  </section>

  <script src="script.js"></script>
</body>
</html>
<head>
<link href="https://fonts.googleapis.com/css2?family=VT323&display=swap" rel="stylesheet" />
<!-- partial -->
  <script  src="./script.js"></script>

</body>
</html>

[Uploading script.js…]()
// Countdown to Jan 1, 2026
const countdownEl = document.getElementById('countdown');
const targetDate = new Date('2026-01-01T00:00:00');

function updateCountdown() {
  const now = new Date();
  const diff = targetDate - now;

  if (diff <= 0) {
    countdownEl.textContent = 'ALBUM OUT NOW!';
    clearInterval(intervalId);
    return;
  }

  const days = Math.floor(diff / (1000 * 60 * 60 * 24));
  const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
  const minutes = Math.floor((diff / (1000 * 60)) % 60);
  const seconds = Math.floor((diff / 1000) % 60);

  countdownEl.textContent = `${days}D ${hours}H ${minutes}M ${seconds}S`;
}

const intervalId = setInterval(updateCountdown, 1000);
updateCountdown();

// Email form submission handler (no backend)
const form = document.getElementById('email-form');
const messageEl = document.getElementById('form-message');

form.addEventListener('submit', (e) => {
  e.preventDefault();
  // Here you would integrate a backend or third-party service like Formspree

  // Just simulate success message for now:
  messageEl.textContent = 'THANKS FOR JOINING THE LIST!';
  form.reset();
});

[style.css](https://github.com/user-attachments/files/21873063/style.css)
/* Background image styling */
.bg-image {
  background: url('https://i.imgur.com/toq30Qz.jpg') no-repeat center center/cover;
  position: fixed;
  top: 0; left: 0; right: 0; bottom: 0;
  z-index: -1;
  filter: grayscale(0%) brightness(0.4);
}

/* Reset and base */
body {
  margin: 0;
  font-family: 'Futura', sans-serif, Arial, sans-serif;
  text-transform: uppercase;
  color: white;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  background-color: black;
  overflow: hidden;
  padding: 1rem;
  text-align: center;
}

/* Band name */
.band-name {
  font-weight: bold;
  font-size: 3rem;
  letter-spacing: 0.3em;
  margin: 0 0 0.5rem;
}

/* Album title */
.album-title {
  font-weight: bold;
  font-size: 2rem;
  letter-spacing: 0.2em;
  margin: 0 0 2rem;
}

.countdown {
  font-family: 'VT323', monospace;
  font-weight: normal;
  font-size: 3rem;
  letter-spacing: 0.15em;
  color: #f5deb3; /* light warm color, like old monitors */
  text-shadow:
    1px 1px 0 #222;
  margin-bottom: 2rem;
}



/* Email form */
.email-form {
  display: flex;
  gap: 1rem;
  justify-content: center;
  flex-wrap: wrap;
}

.email-form input[type="email"] {
  font-family: 'Futura', sans-serif, Arial, sans-serif;
  font-weight: bold;
  text-transform: uppercase;
  padding: 0.5rem 1rem;
  border: none;
  border-radius: 3px;
  font-size: 1rem;
  outline: none;
  min-width: 200px;
}

.email-form button {
  font-family: 'Futura', sans-serif, Arial, sans-serif;
  font-weight: bold;
  text-transform: uppercase;
  padding: 0.5rem 1.5rem;
  border: none;
  border-radius: 3px;
  background-color: white;
  color: black;
  cursor: pointer;
  font-size: 1rem;
  transition: background-color 0.3s ease;
}

.email-form button:hover {
  background-color: #ccc;
}

/* Form message */
#form-message {
  margin-top: 1rem;
  font-size: 1rem;
  color: #ccc;
}
