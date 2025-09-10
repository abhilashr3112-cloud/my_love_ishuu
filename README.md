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
    overflow: hidden;
    position: relative;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
  }

  body::before {
    content: "";
    position: fixed;
    top: 0; left: 0;
    width: 100%; height: 100%;
    background: rgba(0,0,0,0.4);
    z-index: 0;
  }

  .marquee {
    width: 100%;
    overflow: hidden;
    position: fixed;
    top: 0;
    left: 0;
    background: rgba(0,0,0,0.6);
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
  }
  nav a { color: white; margin: 0 15px; text-decoration: none; font-weight: bold; cursor:pointer; }
  nav a:hover { text-decoration: underline; }

  h1 {
    margin: 100px 0 20px 0;
    font-size: 4rem;
    text-shadow: 2px 2px 6px rgba(0,0,0,0.6);
    position: relative;
    z-index: 2;
  }

  /* Sections */
  .page { display: none; width: 100%; flex: 1; justify-content: center; align-items: center; flex-direction: column; }
  .active { display: flex; }

  /* Cards */
  .card-container {
    position: relative;
    width: 80%;
    max-width: 600px;
    height: auto;
    perspective: 1000px;
    z-index: 2;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .card {
    background: #ffffff;
    border: 3px solid #000000;
    border-radius: 15px;
    box-shadow: 0 5px 20px rgba(255,105,180,0.4);
    padding: 30px;
    font-size: 1.3rem;
    line-height: 1.6;
    color: #000000;
    font-style: italic;
    position: absolute;
    top: 0; left: 0; right: 0;
    cursor: pointer;
    transition: transform 0.8s ease, opacity 0.8s ease, box-shadow 0.5s ease, filter 0.5s ease;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
  }
  .card.hide { transform: translateX(120%) rotate(10deg); opacity: 0; }
  .card.show { transform: translateX(0) rotate(0deg); opacity: 1; z-index:2; }
  .card.next { transform: translateX(-120%) rotate(-10deg); opacity:0; }

  /* Memories Page */
  .quote-container {
    background: rgba(255,255,255,0.85);
    color: #000;
    border: 3px solid #000;
    border-radius: 20px;
    padding: 25px;
    font-size: 1.3rem;
    width: 90%;
    max-width: 900px;
    line-height: 1.6;
    text-align: center;
    font-style: italic;
    box-shadow: 0 5px 25px rgba(255,105,180,0.4);
    z-index: 2;
    position: fixed;
    bottom: 20px;
    left: 50%;
    transform: translateX(-50%);
  }

  .anniversary-text {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-size: 3rem;
    font-weight: bold;
    color: #ff4d6d;
    text-shadow: 0 0 10px #ff4d6d, 0 0 20px #fff;
    opacity: 0;
    z-index: 25;
    pointer-events: none;
  }

  .star {
    position: absolute;
    width: 2.5px;
    height: 2.5px;
    background: white;
    border-radius: 50%;
    opacity: 0;
    animation: twinkle 2s infinite alternate;
    z-index: 0;
    box-shadow: 0 0 5px white, 0 0 12px rgba(255,255,255,0.9);
  }
  @keyframes twinkle {
    0% { opacity: 0.3; }
    50% { opacity: 1; }
    100% { opacity: 0.3; }
  }

  @media (max-width: 480px) {
    h1 { font-size: 2.2rem; }
    .marquee span { font-size: 1rem; }
    nav { font-size: 0.8rem; top: 35px; }
    .card { font-size: 0.9rem; padding: 15px; }
    .quote-container { font-size: 1rem; padding: 15px; width: 95%; }
    .anniversary-text { font-size: 2rem; }
  }

</style>
</head>
<body>

<div class="marquee"><span>💖 I Love U Jayaprithvi 💖</span></div>

<nav>
  <a onclick="showPage('page1')">Love</a>
  <a onclick="showPage('page2')">Memories</a>
</nav>

<!-- Page 1: Love Cards -->
<div class="page active" id="page1">
  <h1>I Love U ❤️</h1>
  <div class="card-container">
    <div class="card show">“When I look at you, I see my whole world smiling back at me.”</div>
    <div class="card next">“You’re not just my love, you’re my peace, my strength, and my favorite reason to be happy.”</div>
    <div class="card next">“Every time I hold your hand, I feel like I’m holding the most precious thing in the universe.”</div>
    <div class="card next">“You are the answer to every silent prayer my heart ever made.”</div>
  </div>
</div>

<!-- Page 2: Memories -->
<div class="page" id="page2" style="background: url('memories-bg.jpg') no-repeat center center fixed; background-size: cover;">
  <div class="quote-container">
    “It’s hard to believe that it has already been one whole year since our journey began—a year filled with countless moments that have shaped our story, deepened our bond, and made me realize how extraordinary you truly are...”
  </div>
  <div class="anniversary-text" id="anniversaryText">Happy 1st Year Anniversary Ishu ❤️</div>
</div>

<script>
  // Switch pages
  function showPage(pageId){
    document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
    document.getElementById(pageId).classList.add('active');
  }

  // Twinkling stars for both pages
  for(let i=0;i<100;i++){
    const star = document.createElement('div');
    star.classList.add('star');
    star.style.top = Math.random()*window.innerHeight+'px';
    star.style.left = Math.random()*window.innerWidth+'px';
    star.style.animationDuration = (0.5 + Math.random()*2)+'s';
    document.body.appendChild(star);
  }

  // Greeting cards slide on page1
  const cards = document.querySelectorAll('#page1 .card');
  let current = 0;
  cards.forEach(card=>{
    card.addEventListener('click',()=>{
      cards[current].classList.remove('show');
      cards[current].classList.add('hide');
      current = (current+1)%cards.length;
      setTimeout(()=>{
        cards.forEach((c,i)=>{
          if(i===current){ 
            c.classList.remove('next','hide'); 
            c.classList.add('show'); 
            c.style.zIndex=2; 
          } else { 
            c.classList.remove('show','hide'); 
            c.classList.add('next'); 
            c.style.zIndex=1; 
          }
        });
      },800);
    });
  });

  // Show anniversary text on page2 click
  const text = document.getElementById('anniversaryText');
  document.getElementById('page2').addEventListener('click', ()=> {
    text.style.opacity = 1;
    text.animate([
      { transform: 'translate(-50%, -50%) scale(0.5)', opacity: 0 },
      { transform: 'translate(-50%, -50%) scale(1.2)', opacity: 1 },
      { transform: 'translate(-50%, -50%) scale(1)', opacity: 1 }
    ], { duration: 2000, easing: 'ease-out', fill: 'forwards' });
  });

</script>
</body>
</html>

