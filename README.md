```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Love & Memories</title>
<style>
  body {
    margin: 0;
    font-family: 'Georgia', serif;
    background: url('wallpaper.jpg') no-repeat center center fixed;
    background-size: cover;
    color: white;
    text-align: center;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
    position: relative;
    overflow: hidden;
  }

  body::before {
    content: "";
    position: fixed;
    top: 0; left: 0; width: 100%; height: 100%;
    background: rgba(0,0,0,0.4);
    z-index: 0;
    pointer-events: none;
  }

  .marquee {
    width: 100%;
    overflow: hidden;
    position: fixed;
    top: 0; left: 0;
    background: rgba(0,0,0,0.7);
    padding: 10px 0;
    z-index: 10;
  }
  .marquee span {
    display: inline-block;
    font-size: 1.5rem;
    font-weight: bold;
    white-space: nowrap;
    color: #ff4d6d;
    animation: marquee 15s linear infinite;
    letter-spacing: 2px;
  }
  @keyframes marquee {
    0% { transform: translateX(100%); }
    100% { transform: translateX(-100%); }
  }

  nav {
    background: rgba(0,0,0,0.4);
    padding: 15px;
    position: fixed;
    width: 100%;
    top: 50px;
    z-index: 5;
    display: flex;
    justify-content: center;
  }
  nav a {
    color: white; margin: 0 15px; text-decoration: none;
    font-weight: bold; cursor: pointer; font-size: 1.2rem;
    transition: color 0.3s;
  }
  nav a:hover { color: #ff4d6d; }

  h1 {
    margin: 100px 0 20px 0;
    font-size: 4rem;
    text-shadow: 2px 2px 8px rgba(0,0,0,0.6);
    position: relative;
    z-index: 2;
    letter-spacing
