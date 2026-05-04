<!DOCTYPE html>

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ALEX DAPA™</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Barlow+Condensed:wght@400;600;700;900&family=Barlow:wght@300;400;500&display=swap');

:root {
–yellow: #FFE040;
–black: #0a0a0a;
–white: #F7F4EE;
–gray: #888;
–stripe: repeating-linear-gradient(-45deg, var(–yellow) 0px, var(–yellow) 10px, var(–black) 10px, var(–black) 20px);
}

- { margin: 0; padding: 0; box-sizing: border-box; }
  body { font-family: ‘Barlow Condensed’, sans-serif; background: var(–white); color: var(–black); min-height: 100vh; cursor: crosshair; }

.caution-top { height: 18px; background: var(–stripe); position: fixed; top: 0; left: 0; right: 0; z-index: 999; }

nav {
position: fixed; top: 18px; left: 0; right: 0; z-index: 500;
background: var(–black);
display: flex; align-items: center; justify-content: space-between;
padding: 0 2rem; height: 48px;
border-bottom: 2px solid var(–yellow);
}
.logo { font-family: ‘Bebas Neue’, sans-serif; font-size: 1.6rem; color: var(–white); letter-spacing: 0.1em; line-height: 1; }
.logo span { color: var(–yellow); }
.nav-links { display: flex; gap: 0; list-style: none; }
.nav-links li a {
display: block; padding: 0 1.2rem; height: 48px; line-height: 48px;
text-decoration: none; color: var(–gray);
font-size: 0.72rem; letter-spacing: 0.18em; text-transform: uppercase;
font-weight: 700; cursor: crosshair; transition: all 0.15s;
border-left: 1px solid #222;
}
.nav-links li a::before { content: ‘”’; color: var(–yellow); margin-right: 1px; }
.nav-links li a::after { content: ‘”’; color: var(–yellow); margin-left: 1px; }
.nav-links li a:hover, .nav-links li a.active { color: var(–yellow); background: #111; }
.nav-clock { font-family: ‘Bebas Neue’, sans-serif; font-size: 1.2rem; color: var(–yellow); letter-spacing: 0.08em; }

main { margin-top: 66px; margin-bottom: 64px; }

.hero-bar {
background: var(–yellow); padding: 0.4rem 2rem;
display: flex; align-items: center; justify-content: space-between;
border-bottom: 2px solid var(–black);
}
.hero-bar-text { font-size: 0.62rem; font-weight: 700; letter-spacing: 0.22em; text-transform: uppercase; }

.page { display: none; }
.page.active { display: block; animation: fadein 0.2s ease; }
@keyframes fadein { from { opacity: 0; } to { opacity: 1; } }

.section-header {
display: flex; align-items: flex-end; justify-content: space-between;
padding: 2rem 2rem 1rem; border-bottom: 1px solid #ddd;
}
.section-title { font-family: ‘Bebas Neue’, sans-serif; font-size: 5rem; line-height: 1; letter-spacing: 0.02em; }
.section-title .accent { color: var(–yellow); -webkit-text-stroke: 2px var(–black); }
.section-meta { font-size: 0.62rem; letter-spacing: 0.2em; text-transform: uppercase; color: var(–gray); font-weight: 700; text-align: right; line-height: 2; }

.marquee-wrap { overflow: hidden; background: var(–yellow); border-top: 1px solid var(–black); border-bottom: 1px solid var(–black); white-space: nowrap; padding: 5px 0; }
.marquee-inner { display: inline-block; animation: marquee 20s linear infinite; font-size: 0.62rem; font-weight: 700; letter-spacing: 0.22em; text-transform: uppercase; color: var(–black); }
@keyframes marquee { from { transform: translateX(100vw); } to { transform: translateX(-100%); } }

.photo-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 0; }
.photo-cell {
aspect-ratio: 3/4; background: #e5e1d8;
position: relative; overflow: hidden; cursor: crosshair;
border-right: 1px solid #ccc; border-bottom: 1px solid #ccc;
}
.photo-cell img { width: 100%; height: 100%; object-fit: cover; transition: transform 0.4s ease; display: block; }
.photo-cell:hover img { transform: scale(1.04); }
.photo-cell:hover .cell-overlay { opacity: 1; }
.cell-overlay {
position: absolute; inset: 0; background: rgba(10,10,10,0.8);
display: flex; flex-direction: column; align-items: flex-start; justify-content: flex-end;
padding: 1.2rem; opacity: 0; transition: opacity 0.3s;
}
.cell-cat { font-size: 0.58rem; letter-spacing: 0.25em; text-transform: uppercase; color: var(–yellow); font-weight: 700; margin-bottom: 0.3rem; }
.cell-title { font-family: ‘Bebas Neue’, sans-serif; font-size: 1.5rem; color: var(–white); line-height: 1; letter-spacing: 0.05em; }
.cell-num { position: absolute; top: 0.7rem; right: 0.7rem; font-size: 0.58rem; font-weight: 700; letter-spacing: 0.1em; color: rgba(255,255,255,0.35); background: rgba(0,0,0,0.5); padding: 2px 5px; }
.ph-cell { width: 100%; height: 100%; display: flex; flex-direction: column; align-items: center; justify-content: center; gap: 0.5rem; }
.ph-num { font-family: ‘Bebas Neue’, sans-serif; font-size: 3rem; color: #bbb; line-height: 1; }
.ph-lbl { font-size: 0.58rem; letter-spacing: 0.2em; text-transform: uppercase; color: #aaa; font-weight: 700; }

.stripe-divider { height: 12px; background: var(–stripe); border-top: 1px solid var(–black); border-bottom: 1px solid var(–black); }

/* ABOUT */
.about-grid { display: grid; grid-template-columns: 1fr 1fr; min-height: calc(100vh - 200px); }
.about-left { background: var(–black); padding: 3rem 2.5rem; display: flex; flex-direction: column; justify-content: space-between; position: relative; overflow: hidden; }
.about-left::before { content: ‘AD’; font-family: ‘Bebas Neue’, sans-serif; font-size: 22rem; color: rgba(255,255,255,0.03); position: absolute; bottom: -3rem; left: -1rem; line-height: 1; pointer-events: none; }
.about-tag { display: inline-block; background: var(–yellow); color: var(–black); font-size: 0.58rem; font-weight: 700; letter-spacing: 0.2em; text-transform: uppercase; padding: 3px 8px; margin-bottom: 1.2rem; }
.about-photo { width: 100%; max-width: 340px; aspect-ratio: 3/4; background: #1a1a1a; border: 1px solid #2a2a2a; overflow: hidden; display: flex; align-items: center; justify-content: center; }
.about-photo img { width: 100%; height: 100%; object-fit: cover; }
.about-photo-ph { font-size: 0.62rem; letter-spacing: 0.2em; text-transform: uppercase; color: #333; font-weight: 700; }
.about-footer { font-size: 0.58rem; letter-spacing: 0.18em; text-transform: uppercase; color: #333; font-weight: 700; line-height: 2; }
.about-right { padding: 3rem 2.5rem; display: flex; flex-direction: column; justify-content: space-between; border-left: 1px solid #ddd; }
.about-name { font-family: ‘Bebas Neue’, sans-serif; font-size: 5rem; line-height: 0.95; letter-spacing: 0.02em; margin-bottom: 0.5rem; }
.about-role { font-size: 0.68rem; font-weight: 700; letter-spacing: 0.25em; text-transform: uppercase; color: var(–gray); margin-bottom: 2rem; }
.about-bio { font-family: ‘Barlow’, sans-serif; font-size: 0.9rem; line-height: 1.85; color: #555; margin-bottom: 1.2rem; max-width: 460px; }
.about-quote { font-family: ‘Bebas Neue’, sans-serif; font-size: 1.8rem; line-height: 1.2; border-left: 4px solid var(–yellow); padding-left: 1rem; margin-bottom: 2rem; letter-spacing: 0.02em; }
.about-contact { font-size: 0.62rem; letter-spacing: 0.18em; text-transform: uppercase; color: var(–gray); font-weight: 700; line-height: 2.2; }
.about-contact a { color: var(–black); text-decoration: none; transition: color 0.15s; }
.about-contact a:hover { color: var(–yellow); }

/* PLAYER */
.player { position: fixed; bottom: 0; left: 0; right: 0; height: 56px; background: var(–black); border-top: 2px solid var(–yellow); display: flex; align-items: center; gap: 1rem; padding: 0 1.5rem; z-index: 400; }
.player-label { font-size: 0.55rem; letter-spacing: 0.2em; text-transform: uppercase; color: var(–yellow); font-weight: 700; white-space: nowrap; border: 1px solid var(–yellow); padding: 2px 6px; flex-shrink: 0; }
.play-btn { width: 30px; height: 30px; border-radius: 50%; background: var(–yellow); border: none; cursor: crosshair; display: flex; align-items: center; justify-content: center; flex-shrink: 0; transition: transform 0.15s; }
.play-btn:hover { transform: scale(1.1); }
.play-btn svg { width: 10px; height: 12px; fill: var(–black); margin-left: 1px; }
.ctrl-btn { background: none; border: none; cursor: crosshair; color: #555; font-size: 0.62rem; font-weight: 700; transition: color 0.15s; font-family: ‘Barlow Condensed’, sans-serif; }
.ctrl-btn:hover { color: var(–yellow); }
.track-info { flex: 1; min-width: 0; }
.track-name { font-family: ‘Bebas Neue’, sans-serif; font-size: 1rem; color: var(–white); letter-spacing: 0.08em; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
.track-artist { font-size: 0.58rem; color: #444; letter-spacing: 0.15em; text-transform: uppercase; font-weight: 700; }
.prog-wrap { flex: 2; display: flex; align-items: center; gap: 0.6rem; }
.prog-bar { flex: 1; height: 2px; background: #2a2a2a; cursor: crosshair; position: relative; }
.prog-fill { height: 100%; background: var(–yellow); width: 0%; transition: width 0.4s linear; pointer-events: none; }
.t { font-size: 0.58rem; color: #444; font-variant-numeric: tabular-nums; font-weight: 700; min-width: 28px; font-family: ‘Barlow Condensed’, sans-serif; }
.vol-wrap { display: flex; align-items: center; gap: 0.4rem; }
.vol-wrap svg { width: 12px; height: 12px; fill: #444; flex-shrink: 0; }
input[type=range] { width: 56px; accent-color: var(–yellow); cursor: crosshair; }

.lightbox { display: none; position: fixed; inset: 0; background: rgba(0,0,0,0.93); z-index: 800; align-items: center; justify-content: center; }
.lightbox.open { display: flex; }
.lightbox img { max-width: 88vw; max-height: 88vh; object-fit: contain; }
.lb-close { position: absolute; top: 1.5rem; right: 1.5rem; background: var(–yellow); border: none; font-family: ‘Bebas Neue’, sans-serif; font-size: 1.1rem; padding: 4px 10px; cursor: crosshair; color: var(–black); letter-spacing: 0.1em; }

@media (max-width: 700px) {
.photo-grid { grid-template-columns: repeat(2, 1fr); }
.about-grid { grid-template-columns: 1fr; }
.section-title { font-size: 3.2rem; }
.about-name { font-size: 3.5rem; }
.nav-clock { display: none; }
.player-label { display: none; }
}
</style>

</head>
<body>

<div class="caution-top"></div>

<nav>
  <div class="logo">ALEX<span>DAPA</span>™</div>
  <ul class="nav-links">
    <li><a href="#" onclick="showPage('current',event)" id="nav-current" class="active">CURRENT</a></li>
    <li><a href="#" onclick="showPage('fashion',event)" id="nav-fashion">FASHION</a></li>
    <li><a href="#" onclick="showPage('footwear',event)" id="nav-footwear">FOOTWEAR</a></li>
    <li><a href="#" onclick="showPage('about',event)" id="nav-about">ABOUT ME</a></li>
  </ul>
  <div class="nav-clock" id="nav-clock">00:00:00</div>
</nav>

<main>

  <!-- CURRENT -->

  <div id="page-current" class="page active">
    <div class="hero-bar">
      <span class="hero-bar-text">ALEX DAPA™ &nbsp;·&nbsp; "CREATIVE DIRECTION" &nbsp;·&nbsp; C/O ALEXDAPA.COM</span>
      <span class="hero-bar-text" id="hero-date">—</span>
    </div>
    <div class="section-header">
      <div class="section-title">"CURRENT"<br><span class="accent">WORK</span></div>
      <div class="section-meta">STYLING · FASHION · FOOTWEAR<br>ART DIRECTION · CREATIVE<br>NEW YORK, USA</div>
    </div>
    <div class="marquee-wrap"><div class="marquee-inner">ALEX DAPA™ &nbsp;·&nbsp; "CREATIVE DIRECTION" &nbsp;·&nbsp; FASHION &nbsp;·&nbsp; FOOTWEAR &nbsp;·&nbsp; STYLING &nbsp;·&nbsp; ART DIRECTION &nbsp;·&nbsp; NEW YORK &nbsp;·&nbsp; ALEXDAPA.COM &nbsp;·&nbsp; ALEX DAPA™ &nbsp;·&nbsp; "CREATIVE DIRECTION" &nbsp;·&nbsp; FASHION &nbsp;·&nbsp; FOOTWEAR &nbsp;·&nbsp; STYLING &nbsp;·&nbsp; ART DIRECTION &nbsp;·&nbsp; NEW YORK &nbsp;·&nbsp; ALEXDAPA.COM &nbsp;·&nbsp;</div></div>
    <div class="photo-grid">
      <!-- ADD YOUR IMAGES HERE. Example:
      <div class="photo-cell" onclick="openLight('images/photo.jpg')">
        <img src="images/photo.jpg" alt="">
        <div class="cell-overlay"><div class="cell-cat">2025</div><div class="cell-title">TITLE</div></div>
        <div class="cell-num">001</div>
      </div> -->
      <div class="photo-cell"><div class="ph-cell"><div class="ph-num">001</div><div class="ph-lbl">Add Image</div></div></div>
      <div class="photo-cell"><div class="ph-cell"><div class="ph-num">002</div><div class="ph-lbl">Add Image</div></div></div>
      <div class="photo-cell"><div class="ph-cell"><div class="ph-num">003</div><div class="ph-lbl">Add Image</div></div></div>
      <div class="photo-cell"><div class="ph-cell"><div class="ph-num">004</div><div class="ph-lbl">Add Image</div></div></div>
      <div class="photo-cell"><div class="ph-cell"><div class="ph-num">005</div><div class="ph-lbl">Add Image</div></div></div>
      <div class="photo-cell"><div class="ph-cell"><div class="ph-num">006</div><div class="ph-lbl">Add Image</div></div></div>
    </div>
  </div>

  <!-- FASHION -->

  <div id="page-fashion" class="page">
    <div class="hero-bar"><span class="hero-bar-text">ALEX DAPA™ &nbsp;·&nbsp; "FASHION" &nbsp;·&nbsp; EDITORIAL · CAMPAIGN · LOOKBOOK</span></div>
    <div class="section-header">
      <div class="section-title">"FASHION"<br><span class="accent">EDIT</span></div>
      <div class="section-meta">EDITORIAL<br>CAMPAIGN<br>LOOKBOOK</div>
    </div>
    <div class="stripe-divider"></div>
    <div class="photo-grid">
      <div class="photo-cell"><div class="ph-cell"><div class="ph-num">001</div><div class="ph-lbl">Add Image</div></div></div>
      <div class="photo-cell"><div class="ph-cell"><div class="ph-num">002</div><div class="ph-lbl">Add Image</div></div></div>
      <div class="photo-cell"><div class="ph-cell"><div class="ph-num">003</div><div class="ph-lbl">Add Image</div></div></div>
      <div class="photo-cell"><div class="ph-cell"><div class="ph-num">004</div><div class="ph-lbl">Add Image</div></div></div>
      <div class="photo-cell"><div class="ph-cell"><div class="ph-num">005</div><div class="ph-lbl">Add Image</div></div></div>
      <div class="photo-cell"><div class="ph-cell"><div class="ph-num">006</div><div class="ph-lbl">Add Image</div></div></div>
    </div>
  </div>

  <!-- FOOTWEAR -->

  <div id="page-footwear" class="page">
    <div class="hero-bar"><span class="hero-bar-text">ALEX DAPA™ &nbsp;·&nbsp; "FOOTWEAR" &nbsp;·&nbsp; DESIGN · CAMPAIGN · DIRECTION</span></div>
    <div class="section-header">
      <div class="section-title">"FOOT<br><span class="accent">WEAR"</span></div>
      <div class="section-meta">DESIGN<br>CAMPAIGN<br>DIRECTION</div>
    </div>
    <div class="stripe-divider"></div>
    <div class="photo-grid">
      <div class="photo-cell"><div class="ph-cell"><div class="ph-num">001</div><div class="ph-lbl">Add Image</div></div></div>
      <div class="photo-cell"><div class="ph-cell"><div class="ph-num">002</div><div class="ph-lbl">Add Image</div></div></div>
      <div class="photo-cell"><div class="ph-cell"><div class="ph-num">003</div><div class="ph-lbl">Add Image</div></div></div>
      <div class="photo-cell"><div class="ph-cell"><div class="ph-num">004</div><div class="ph-lbl">Add Image</div></div></div>
    </div>
  </div>

  <!-- ABOUT -->

  <div id="page-about" class="page">
    <div class="hero-bar"><span class="hero-bar-text">ALEX DAPA™ &nbsp;·&nbsp; "ABOUT ME" &nbsp;·&nbsp; CREATIVE DIRECTOR · NEW YORK</span></div>
    <div class="about-grid">
      <div class="about-left">
        <div>
          <div class="about-tag">c/o ALEX DAPA™</div>
          <div class="about-photo">
            <!-- <img src="images/alex.jpg" alt="Alex Dapa"> -->
            <div class="about-photo-ph">PHOTO HERE</div>
          </div>
        </div>
        <div class="about-footer">FOR DISPLAY<br>PURPOSES ONLY™</div>
      </div>
      <div class="about-right">
        <div>
          <div class="about-name">ALEX<br>DAPA</div>
          <div class="about-role">"CREATIVE DIRECTOR" &nbsp;·&nbsp; STYLIST &nbsp;·&nbsp; ART DIRECTOR</div>
          <p class="about-bio">Write your bio here — who you are, your background in fashion, footwear, and styling. What drives you creatively and what makes your work distinct.</p>
          <p class="about-bio">A second paragraph about your experience — clients, NYFW work, collaborations, or your artistic approach.</p>
          <div class="about-quote">"THE SPACE BETWEEN<br>ART AND FASHION"</div>
        </div>
        <div class="about-contact">
          BASED IN NEW YORK, USA<br>
          <a href="mailto:alex@alexdapa.com">ALEX@ALEXDAPA.COM</a><br>
          <a href="#">@ALEXDAPA</a><br>
          ALEXDAPA.COM
        </div>
      </div>
    </div>
  </div>

</main>

<div class="lightbox" id="lightbox" onclick="closeLight(event)">
  <button class="lb-close" onclick="document.getElementById('lightbox').classList.remove('open')">CLOSE ✕</button>
  <img id="lb-img" src="" alt="">
</div>

<div class="player">
  <div class="player-label">NOW PLAYING</div>
  <button class="ctrl-btn" onclick="prevTrack()">◀◀</button>
  <button class="play-btn" id="play-btn" onclick="togglePlay()">
    <svg id="play-icon" viewBox="0 0 10 12"><polygon points="0,0 10,6 0,12"/></svg>
  </button>
  <button class="ctrl-btn" onclick="nextTrack()">▶▶</button>
  <div class="track-info">
    <div class="track-name" id="track-name">NO TRACK LOADED</div>
    <div class="track-artist" id="track-artist">ADD AUDIO FILES TO TRACKS ARRAY</div>
  </div>
  <div class="prog-wrap">
    <span class="t" id="t-cur">0:00</span>
    <div class="prog-bar" onclick="seek(event)"><div class="prog-fill" id="prog-fill"></div></div>
    <span class="t" id="t-dur">0:00</span>
  </div>
  <div class="vol-wrap">
    <svg viewBox="0 0 16 16"><path d="M3 5H1v6h2l4 4V1L3 5zm9.5 3A4.5 4.5 0 009 4v8a4.5 4.5 0 003.5-4.5z"/></svg>
    <input type="range" min="0" max="1" step="0.01" value="1" oninput="audio.volume=this.value">
  </div>
</div>

<script>
  function tick() {
    const n = new Date(), p = x => String(x).padStart(2,'0');
    const h = n.getHours(), m = n.getMinutes(), s = n.getSeconds();
    const ap = h >= 12 ? 'PM' : 'AM', h12 = h % 12 || 12;
    document.getElementById('nav-clock').textContent = `${p(h12)}:${p(m)}:${p(s)} ${ap}`;
    const D = ['SUN','MON','TUE','WED','THU','FRI','SAT'], M = ['JAN','FEB','MAR','APR','MAY','JUN','JUL','AUG','SEP','OCT','NOV','DEC'];
    const d = document.getElementById('hero-date');
    if (d) d.textContent = `${D[n.getDay()]} ${M[n.getMonth()]} ${n.getDate()} ${n.getFullYear()}`;
  }
  tick(); setInterval(tick, 1000);

  function showPage(name, e) {
    if (e) e.preventDefault();
    document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
    document.querySelectorAll('.nav-links a').forEach(a => a.classList.remove('active'));
    document.getElementById('page-' + name).classList.add('active');
    document.getElementById('nav-' + name).classList.add('active');
    window.scrollTo(0, 0);
  }

  function openLight(src) {
    if (!src) return;
    document.getElementById('lb-img').src = src;
    document.getElementById('lightbox').classList.add('open');
  }
  function closeLight(e) {
    if (e.target === document.getElementById('lightbox')) document.getElementById('lightbox').classList.remove('open');
  }

  /*
    HOW TO ADD MUSIC:
    Replace empty src strings with paths to your audio files.
    Put mp3s in an "audio/" folder next to index.html.
    Example: { title: "SONG NAME", artist: "ARTIST", src: "audio/track1.mp3" }
  */
  const tracks = [
    { title: "TRACK ONE", artist: "ARTIST NAME", src: "" },
    { title: "TRACK TWO", artist: "ARTIST NAME", src: "" },
    { title: "TRACK THREE", artist: "ARTIST NAME", src: "" },
  ];

  let cur = 0, playing = false;
  const audio = new Audio();
  audio.ontimeupdate = () => {
    if (!audio.duration) return;
    document.getElementById('prog-fill').style.width = (audio.currentTime / audio.duration * 100) + '%';
    document.getElementById('t-cur').textContent = fmt(audio.currentTime);
  };
  audio.onloadedmetadata = () => document.getElementById('t-dur').textContent = fmt(audio.duration);
  audio.onended = () => nextTrack();
  function fmt(s) { const m = Math.floor(s/60), x = Math.floor(s%60); return m+':'+(x<10?'0':'')+x; }
  function loadTrack(i, play) {
    cur = i;
    document.getElementById('track-name').textContent = tracks[i].title;
    document.getElementById('track-artist').textContent = tracks[i].artist;
    if (tracks[i].src) { audio.src = tracks[i].src; if (play) { audio.play(); playing = true; } }
    updateBtn();
  }
  function togglePlay() {
    if (!tracks[cur].src) return;
    if (playing) { audio.pause(); playing = false; } else { audio.play(); playing = true; }
    updateBtn();
  }
  function updateBtn() {
    document.getElementById('play-icon').innerHTML = playing
      ? '<rect x="1" y="0" width="3" height="12"/><rect x="6" y="0" width="3" height="12"/>'
      : '<polygon points="0,0 10,6 0,12"/>';
  }
  function nextTrack() { loadTrack((cur + 1) % tracks.length, playing); }
  function prevTrack() { loadTrack((cur - 1 + tracks.length) % tracks.length, playing); }
  function seek(e) {
    if (!audio.duration) return;
    const b = e.currentTarget.getBoundingClientRect();
    audio.currentTime = ((e.clientX - b.left) / b.width) * audio.duration;
  }
  loadTrack(0, false);
</script>

</body>
</html>
