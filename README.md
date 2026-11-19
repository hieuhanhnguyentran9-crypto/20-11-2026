<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Chúc Mừng 20/11 - Tập Thể 9A2 & Thầy Hiếu</title>
<link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@500;600;700&family=Patrick+Hand&family=Quicksand:wght@500;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --blue-dark: #33529c;
    --blue-mid: #7d9cd6;
    --blue-light: #c9d9f8;
    --blue-pastel: #e4ecfc;
    --pink-pastel: #f7d6e0;
    --cream: #f4efe6;
    --text-main: #2a4380;
  }

  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    user-select: none;
  }

  body {
    font-family: 'Quicksand', sans-serif;
    color: var(--text-main);
    background-color: var(--cream);
    overflow-x: hidden;
    min-height: 100vh;
  }

  /* ================= MÀN HÌNH MỞ ĐẦU HOA NỞ ================= */
  #intro-screen {
    position: fixed;
    inset: 0;
    background-color: #f3ede2;
    z-index: 9999;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    overflow: hidden;
    transition: opacity 0.8s ease, visibility 0.8s ease;
  }

  #intro-screen.hidden {
    opacity: 0;
    visibility: hidden;
    pointer-events: none;
  }

  #flower-canvas {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
  }

  .envelope-trigger {
    position: relative;
    z-index: 10;
    cursor: pointer;
    transition: transform 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
    animation: floatEnvelope 2.5s ease-in-out infinite;
    text-align: center;
  }

  .envelope-trigger:hover {
    transform: scale(1.08);
  }

  @keyframes floatEnvelope {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-10px); }
  }

  .envelope-hint {
    margin-top: 14px;
    font-family: 'Patrick Hand', cursive;
    font-size: 1.3rem;
    color: #7c6f64;
    letter-spacing: 0.5px;
  }

  #tap-to-reveal {
    position: relative;
    z-index: 20;
    opacity: 0;
    transform: scale(0.8);
    pointer-events: none;
    transition: all 0.6s cubic-bezier(0.34, 1.56, 0.64, 1);
    background: rgba(255, 255, 255, 0.92);
    backdrop-filter: blur(6px);
    padding: 16px 36px;
    border-radius: 50px;
    border: 3px solid var(--blue-dark);
    box-shadow: 0 10px 30px rgba(51, 82, 156, 0.25);
    cursor: pointer;
    font-family: 'Fredoka', sans-serif;
    font-size: 1.5rem;
    color: var(--blue-dark);
  }

  #tap-to-reveal.show {
    opacity: 1;
    transform: scale(1);
    pointer-events: auto;
    animation: pulseBtn 1.8s infinite;
  }

  @keyframes pulseBtn {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.06); }
  }

  /* ================= THANH ĐIỀU HƯỚNG ================= */
  header {
    position: sticky;
    top: 0;
    z-index: 100;
    background: rgba(255, 255, 255, 0.94);
    backdrop-filter: blur(8px);
    border-bottom: 2px solid var(--blue-light);
    padding: 12px 24px;
    display: flex;
    justify-content: flex-end;
    align-items: center;
    gap: 20px;
    flex-wrap: wrap;
  }

  .nav-btn {
    background: none;
    border: none;
    font-family: 'Fredoka', sans-serif;
    font-size: 1rem;
    color: var(--blue-mid);
    cursor: pointer;
    padding: 6px 12px;
    border-radius: 20px;
    transition: all 0.25s ease;
    text-transform: uppercase;
    letter-spacing: 0.5px;
  }

  .nav-btn:hover, .nav-btn.active {
    color: var(--blue-dark);
    background-color: var(--blue-pastel);
    font-weight: 700;
  }

  /* ================= CÁC MÀN HÌNH NỘI DUNG ================= */
  .page-section {
    display: none;
    min-height: calc(100vh - 58px);
    padding: 40px 20px 60px;
    animation: fadeInPage 0.5s ease;
  }

  .page-section.active {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  @keyframes fadeInPage {
    from { opacity: 0; transform: translateY(12px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* HỌA TIẾT NỀN */
  .bg-dots-sky {
    background-color: #f8faff;
    background-image: 
      radial-gradient(#c3d5f8 2px, transparent 2px),
      radial-gradient(#dce6fa 2px, #f8faff 2px);
    background-size: 40px 40px;
    background-position: 0 0, 20px 20px;
  }

  .bg-gingham-blue {
    background-color: #e9effb;
    background-image:
      linear-gradient(90deg, rgba(125, 156, 214, 0.28) 50%, transparent 50%),
      linear-gradient(rgba(125, 156, 214, 0.28) 50%, transparent 50%);
    background-size: 64px 64px;
  }

  .bg-stripes-retro {
    background: repeating-linear-gradient(
      90deg,
      #8da8dc 0px,
      #8da8dc 48px,
      #f6f0e4 48px,
      #f6f0e4 96px
    );
  }

  /* ================= TRANG 1: TRANG CHỦ 20/11 ================= */
  .hero-container {
    max-width: 1000px;
    width: 100%;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 30px;
    align-items: center;
    text-align: center;
  }

  .hero-title {
    font-family: 'Fredoka', sans-serif;
    font-size: clamp(2.4rem, 5vw, 3.8rem);
    color: var(--blue-dark);
    line-height: 1.15;
    margin-bottom: 16px;
    text-shadow: 3px 3px 0px #ffffff, 5px 5px 0px var(--blue-light);
  }

  .hero-subtitle {
    font-family: 'Patrick Hand', cursive;
    font-size: 1.5rem;
    color: #5572b5;
    margin-bottom: 20px;
  }

  .cat-mascot-box {
    position: relative;
    display: inline-block;
    animation: gentleWobble 3s ease-in-out infinite;
  }

  @keyframes gentleWobble {
    0%, 100% { transform: rotate(-2deg); }
    50% { transform: rotate(2deg); }
  }

  .gift-box-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .open-me-btn {
    margin-top: 18px;
    background: #ffffff;
    color: var(--blue-dark);
    border: 3px solid var(--blue-dark);
    font-family: 'Fredoka', sans-serif;
    font-size: 1.4rem;
    padding: 12px 42px;
    border-radius: 50px;
    cursor: pointer;
    box-shadow: 0 6px 0 var(--blue-dark);
    transition: all 0.2s ease;
  }

  .open-me-btn:hover {
    transform: translateY(-2px);
    background: var(--blue-pastel);
  }

  /* ================= TRANG 2: CHỌN MÓN QUÀ ================= */
  .section-heading {
    font-family: 'Fredoka', sans-serif;
    font-size: clamp(2rem, 4vw, 3rem);
    color: var(--blue-dark);
    background: rgba(255, 255, 255, 0.9);
    padding: 12px 32px;
    border-radius: 30px;
    border: 3px solid var(--blue-dark);
    box-shadow: 0 6px 0 var(--blue-mid);
    margin-bottom: 40px;
    text-align: center;
  }

  .hearts-grid {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 36px;
    max-width: 1050px;
  }

  .heart-card {
    display: flex;
    flex-direction: column;
    align-items: center;
    cursor: pointer;
    transition: transform 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
  }

  .heart-card:hover {
    transform: translateY(-10px) scale(1.04);
  }

  .heart-shape-box {
    width: 240px;
    height: 220px;
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    filter: drop-shadow(0 8px 12px rgba(51, 82, 156, 0.2));
  }

  .heart-pill-btn {
    margin-top: 14px;
    background: #ffffff;
    border: 3px solid var(--blue-dark);
    color: var(--blue-dark);
    font-family: 'Fredoka', sans-serif;
    font-size: 1.3rem;
    padding: 8px 34px;
    border-radius: 30px;
    box-shadow: 0 5px 0 var(--blue-dark);
  }

  /* ================= KHUNG ẢNH CỐ ĐỊNH ================= */
  .photo-display-frame {
    background: #ffffff;
    padding: 8px 8px 28px 8px;
    border-radius: 12px;
    border: 2.5px solid var(--blue-dark);
    box-shadow: 0 8px 18px rgba(51, 82, 156, 0.18);
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    overflow: hidden;
    transition: transform 0.25s ease;
  }

  .photo-display-frame:hover {
    transform: scale(1.03) rotate(-1deg);
  }

  .photo-inner {
    width: 100%;
    height: calc(100% - 24px);
    border-radius: 6px;
    overflow: hidden;
    position: relative;
    background: var(--blue-pastel);
  }

  .photo-inner img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .photo-caption {
    position: absolute;
    bottom: 5px;
    font-family: 'Patrick Hand', cursive;
    font-size: 0.95rem;
    color: var(--blue-dark);
  }

  /* ================= TRANG 3: THƯ CHÚC MỪNG ================= */
  .letter-layout {
    max-width: 960px;
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
    gap: 30px;
  }

  .letter-photo-box {
    width: 240px;
    height: 290px;
    transform: rotate(-3deg);
  }

  .letter-paper {
    flex: 1;
    min-width: 310px;
    max-width: 560px;
    background: var(--pink-pastel);
    border: 3px solid var(--blue-dark);
    border-radius: 20px;
    padding: 32px 28px;
    position: relative;
    box-shadow: 10px 10px 0 var(--blue-mid);
  }

  .letter-header-badge {
    display: inline-block;
    background: #ffffff;
    border: 2.5px solid var(--blue-dark);
    color: var(--blue-dark);
    font-family: 'Fredoka', sans-serif;
    font-size: 1.5rem;
    padding: 6px 24px;
    border-radius: 30px;
    margin-bottom: 18px;
  }

  .letter-body {
    font-family: 'Patrick Hand', cursive;
    font-size: 1.38rem;
    line-height: 1.6;
    color: #243b73;
  }

  .editable-name {
    display: inline-block;
    background: rgba(255, 255, 255, 0.7);
    border-bottom: 2px dashed var(--blue-dark);
    padding: 2px 10px;
    border-radius: 6px;
    font-weight: 700;
  }

  /* ================= TRANG 4: HOA TƯƠI ================= */
  .flowers-layout {
    max-width: 980px;
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
    gap: 28px;
  }

  .flower-message-card {
    background: #ffffff;
    border: 4px solid var(--blue-dark);
    border-radius: 28px;
    padding: 32px;
    max-width: 400px;
    position: relative;
    box-shadow: 0 10px 0 var(--blue-light);
    font-family: 'Fredoka', sans-serif;
    font-size: 1.55rem;
    line-height: 1.45;
    color: var(--blue-dark);
  }

  .flower-photo-box {
    width: 240px;
    height: 290px;
    transform: rotate(3deg);
  }

  /* ================= TRANG 5: BÁNH TRI ÂN & 9A2 BLOGSPOT ================= */
  .cake-stage {
    max-width: 980px;
    width: 100%;
    background: rgba(255, 255, 255, 0.92);
    border: 4px solid var(--blue-dark);
    border-radius: 28px;
    padding: 30px 24px;
    box-shadow: 0 12px 0 var(--blue-dark);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 28px;
  }

  .cake-top-row {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    align-items: center;
    gap: 24px;
  }

  .memory-frames-col {
    display: flex;
    gap: 16px;
    flex-wrap: wrap;
    justify-content: center;
  }

  .cake-photo-box {
    width: 175px;
    height: 215px;
  }

  .blog-link-box {
    background: var(--blue-pastel);
    border: 3px solid var(--blue-dark);
    border-radius: 20px;
    padding: 20px 28px;
    display: flex;
    align-items: center;
    gap: 20px;
    flex-wrap: wrap;
    justify-content: center;
    text-align: center;
    width: 100%;
    max-width: 700px;
  }

  .visit-blog-btn {
    background: var(--blue-dark);
    color: #ffffff;
    font-family: 'Fredoka', sans-serif;
    font-size: 1.1rem;
    padding: 10px 24px;
    border-radius: 30px;
    text-decoration: none;
    box-shadow: 0 4px 0 #182548;
    transition: transform 0.2s;
    display: inline-block;
  }

  .visit-blog-btn:hover {
    transform: translateY(-2px);
    background: #22386e;
  }

  .vinyl-box {
    background: var(--blue-pastel);
    border: 3px solid var(--blue-dark);
    border-radius: 20px;
    padding: 18px 26px;
    display: flex;
    align-items: center;
    gap: 20px;
    flex-wrap: wrap;
    justify-content: center;
    width: 100%;
    max-width: 700px;
  }

  .vinyl-disc {
    width: 120px;
    height: 120px;
    border-radius: 50%;
    background: radial-gradient(circle, #ffffff 14%, var(--blue-dark) 15%, #1d2d58 45%, #3a569c 47%, #182548 100%);
    border: 4px solid #ffffff;
    box-shadow: 0 6px 15px rgba(0,0,0,0.25);
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    position: relative;
  }

  .vinyl-disc.playing {
    animation: spinDisc 4s linear infinite;
  }

  @keyframes spinDisc {
    100% { transform: rotate(360deg); }
  }

  .vinyl-label {
    background: #ffffff;
    color: var(--blue-dark);
    font-family: 'Fredoka', sans-serif;
    font-size: 0.78rem;
    padding: 6px 10px;
    border-radius: 20px;
    text-align: center;
    pointer-events: none;
  }

  /* NÚT QUAY LẠI */
  .back-arrow-btn {
    margin-top: 28px;
    background: #ffffff;
    border: 3px solid var(--blue-dark);
    color: var(--blue-dark);
    font-family: 'Fredoka', sans-serif;
    font-size: 1.15rem;
    padding: 10px 26px;
    border-radius: 40px;
    cursor: pointer;
    display: inline-flex;
    align-items: center;
    gap: 8px;
    box-shadow: 0 5px 0 var(--blue-dark);
    transition: transform 0.2s;
  }

  .back-arrow-btn:hover {
    transform: translateX(-4px);
    background: var(--blue-pastel);
  }

  @media (max-width: 768px) {
    .hero-container {
      grid-template-columns: 1fr;
    }
    header {
      justify-content: center;
      gap: 8px;
    }
    .nav-btn {
      font-size: 0.85rem;
      padding: 5px 8px;
    }
  }
</style>
</head>
<body>

  <!-- ================= MÀN HÌNH MỞ ĐẦU HOA NỞ ================= -->
  <div id="intro-screen">
    <canvas id="flower-canvas"></canvas>

    <div class="envelope-trigger" id="envelope-btn" onclick="startFlowerBloom()">
      <svg width="160" height="115" viewBox="0 0 160 115" fill="none">
        <ellipse cx="80" cy="108" rx="62" ry="6" fill="rgba(160, 145, 125, 0.25)"/>
        <rect x="12" y="12" width="136" height="90" rx="8" fill="#efe6d5" stroke="#c8b99e" stroke-width="2.5"/>
        <path d="M14 14L80 62L146 14" stroke="#cbbba0" stroke-width="2.5" fill="#e7dcc8"/>
        <path d="M14 100L62 56M146 100L98 56" stroke="#d5c7af" stroke-width="2"/>
        <path d="M80 42V22M80 34L68 26M80 32L92 25" stroke="#6c9a68" stroke-width="2" stroke-linecap="round"/>
        <circle cx="80" cy="20" r="4" fill="#e67e96"/>
        <circle cx="67" cy="25" r="3.5" fill="#f3b749"/>
        <circle cx="93" cy="24" r="3.5" fill="#82a6df"/>
        <circle cx="80" cy="58" r="10" fill="#b49fcc" stroke="#967eb3" stroke-width="2"/>
        <path d="M77 58C77 56 80 55 80 57.5C80 55 83 56 83 58C83 60.5 80 62 80 62C80 62 77 60.5 77 58Z" fill="#f5eefc"/>
      </svg>
      <div class="envelope-hint">Chạm vào phong bì nhé ✨</div>
    </div>

    <button id="tap-to-reveal" onclick="enterMainSite()">✨ Chạm để mở quà 20/11 ✨</button>
  </div>

  <!-- ================= THANH MENU TRÊN CÙNG ================= -->
  <header>
    <button class="nav-btn active" onclick="showPage('home', this)">20/11</button>
    <button class="nav-btn" onclick="showPage('surprise', this)">Món Quà</button>
    <button class="nav-btn" onclick="showPage('message', this)">Lời Chúc</button>
    <button class="nav-btn" onclick="showPage('flowers', this)">Hoa Tươi</button>
    <button class="nav-btn" onclick="showPage('cake', this)">Tri Ân</button>
  </header>

  <!-- ================= TRANG 1: TRANG CHỦ 20/11 ================= -->
  <section id="home" class="page-section bg-dots-sky active">
    <div class="hero-container">
      <div>
        <h1 class="hero-title">HAPPY<br>TEACHERS' DAY<br>20/11</h1>
        <p class="hero-subtitle">Tập thể 9A2 chúc mừng Thầy Hiếu 💙</p>

        <div class="cat-mascot-box">
          <svg width="210" height="210" viewBox="0 0 210 210" fill="none">
            <g fill="#7d9cd6" opacity="0.6">
              <circle cx="28" cy="65" r="7"/><circle cx="20" cy="54" r="3"/><circle cx="28" cy="51" r="3"/><circle cx="36" cy="54" r="3"/>
              <circle cx="182" cy="145" r="7"/><circle cx="174" cy="134" r="3"/><circle cx="182" cy="131" r="3"/><circle cx="190" cy="134" r="3"/>
            </g>
            <path d="M55 95L45 55L82 75C96 71 114 71 128 75L165 55L155 95C165 110 165 135 152 150C138 166 72 166 58 150C45 135 45 110 55 95Z" fill="#f5efe6" stroke="#33529c" stroke-width="4"/>
            <path d="M105 73V86M95 75L97 85M115 75L113 85" stroke="#8c9bb8" stroke-width="3" stroke-linecap="round"/>
            <circle cx="84" cy="112" r="6" fill="#33529c"/>
            <circle cx="126" cy="112" r="6" fill="#33529c"/>
            <circle cx="82" cy="110" r="2" fill="#fff"/>
            <circle cx="124" cy="110" r="2" fill="#fff"/>
            <ellipse cx="105" cy="122" rx="5" ry="3.5" fill="#e58ca4"/>
            <path d="M97 129C101 134 105 130 105 126C105 130 109 134 113 129" stroke="#33529c" stroke-width="3" stroke-linecap="round"/>
            <ellipse cx="72" cy="123" rx="8" ry="5" fill="#f7c2d0"/>
            <ellipse cx="138" cy="123" rx="8" ry="5" fill="#f7c2d0"/>
            <polygon points="105,22 152,42 105,62 58,42" fill="#33529c" stroke="#22386e" stroke-width="3"/>
            <rect x="83" y="49" width="44" height="16" rx="4" fill="#4c70c2" stroke="#22386e" stroke-width="2.5"/>
            <path d="M148 43V66" stroke="#f4c44e" stroke-width="3" stroke-linecap="round"/>
            <circle cx="148" cy="68" r="4" fill="#f4c44e"/>
          </svg>
        </div>
      </div>

      <div class="gift-box-wrapper">
        <svg width="290" height="270" viewBox="0 0 290 270" fill="none">
          <path d="M72 95C72 125 90 140 105 155" stroke="#7d9cd6" stroke-width="2"/>
          <ellipse cx="68" cy="65" rx="26" ry="32" fill="#7d9cd6" stroke="#33529c" stroke-width="3"/>
          <path d="M220 90C220 120 200 135 185 155" stroke="#33529c" stroke-width="2"/>
          <ellipse cx="224" cy="60" rx="28" ry="34" fill="#33529c" stroke="#22386e" stroke-width="3"/>
          <ellipse cx="145" cy="45" rx="24" ry="29" fill="#c9d9f8" stroke="#33529c" stroke-width="3"/>
          <rect x="75" y="135" width="140" height="115" rx="10" fill="#dce7fc" stroke="#33529c" stroke-width="4"/>
          <rect x="131" y="135" width="28" height="115" fill="#33529c"/>
          <rect x="65" y="112" width="160" height="28" rx="8" fill="#eef4ff" stroke="#33529c" stroke-width="4"/>
          <rect x="131" y="112" width="28" height="28" fill="#33529c"/>
          <path d="M145 112C120 82 88 92 98 112H145Z" fill="#4f74c9" stroke="#33529c" stroke-width="3.5"/>
          <path d="M145 112C170 82 202 92 192 112H145Z" fill="#4f74c9" stroke="#33529c" stroke-width="3.5"/>
          <circle cx="145" cy="110" r="11" fill="#33529c"/>
        </svg>

        <button class="open-me-btn" onclick="goToPage('surprise')">Mở quà ngay 🎁</button>
      </div>
    </div>
  </section>

  <!-- ================= TRANG 2: CHỌN 3 MÓN QUÀ ================= -->
  <section id="surprise" class="page-section bg-gingham-blue">
    <h2 class="section-heading">Món Quà Tri Ân Dành Tặng Thầy HIẾU!</h2>

    <div class="hearts-grid">
      <div class="heart-card" onclick="goToPage('message')">
        <div class="heart-shape-box">
          <svg width="240" height="220" viewBox="0 0 240 220">
            <path d="M120 202C120 202 22 140 22 72C22 38 48 16 78 16C98 16 112 28 120 42C128 28 142 16 162 16C192 16 218 38 218 72C218 140 120 202 120 202Z" fill="#99b5e8" stroke="#33529c" stroke-width="5"/>
            <path d="M120 182C120 182 42 130 42 76C42 50 60 34 82 34C98 34 111 44 120 56C129 44 142 34 158 34C180 34 198 50 198 76C198 130 120 182 120 182Z" fill="#ffffff"/>
            <rect x="82" y="78" width="76" height="52" rx="6" fill="#dce7fc" stroke="#33529c" stroke-width="3.5"/>
            <path d="M84 80L120 108L156 80" stroke="#33529c" stroke-width="3.5" fill="none"/>
            <circle cx="120" cy="105" r="7" fill="#e58ca4"/>
          </svg>
        </div>
        <div class="heart-pill-btn">Lời Chúc</div>
      </div>

      <div class="heart-card" onclick="goToPage('flowers')">
        <div class="heart-shape-box">
          <svg width="240" height="220" viewBox="0 0 240 220">
            <path d="M120 202C120 202 22 140 22 72C22 38 48 16 78 16C98 16 112 28 120 42C128 28 142 16 162 16C192 16 218 38 218 72C218 140 120 202 120 202Z" fill="#f3becd" stroke="#33529c" stroke-width="5"/>
            <path d="M120 182C120 182 42 130 42 76C42 50 60 34 82 34C98 34 111 44 120 56C129 44 142 34 158 34C180 34 198 50 198 76C198 130 120 182 120 182Z" fill="#ffffff"/>
            <polygon points="95,98 145,98 130,148 110,148" fill="#c9d9f8" stroke="#33529c" stroke-width="3"/>
            <circle cx="105" cy="86" r="14" fill="#f7a8be" stroke="#33529c" stroke-width="2.5"/>
            <circle cx="135" cy="86" r="14" fill="#f7a8be" stroke="#33529c" stroke-width="2.5"/>
            <circle cx="120" cy="74" r="15" fill="#ffd3df" stroke="#33529c" stroke-width="2.5"/>
          </svg>
        </div>
        <div class="heart-pill-btn">Hoa Tươi</div>
      </div>

      <div class="heart-card" onclick="goToPage('cake')">
        <div class="heart-shape-box">
          <svg width="240" height="220" viewBox="0 0 240 220">
            <path d="M120 202C120 202 22 140 22 72C22 38 48 16 78 16C98 16 112 28 120 42C128 28 142 16 162 16C192 16 218 38 218 72C218 140 120 202 120 202Z" fill="#99b5e8" stroke="#33529c" stroke-width="5"/>
            <path d="M120 182C120 182 42 130 42 76C42 50 60 34 82 34C98 34 111 44 120 56C129 44 142 34 158 34C180 34 198 50 198 76C198 130 120 182 120 182Z" fill="#ffffff"/>
            <rect x="85" y="102" width="70" height="36" rx="6" fill="#dce7fc" stroke="#33529c" stroke-width="3.5"/>
            <rect x="97" y="80" width="46" height="22" rx="5" fill="#f7d6e0" stroke="#33529c" stroke-width="3"/>
            <line x1="120" y1="64" x2="120" y2="80" stroke="#33529c" stroke-width="3.5"/>
            <circle cx="120" cy="59" r="5" fill="#ffb84d"/>
          </svg>
        </div>
        <div class="heart-pill-btn">Tri Ân</div>
      </div>
    </div>

    <button class="back-arrow-btn" onclick="goToPage('home')">⬅ Quay lại trang đầu</button>
  </section>

  <!-- ================= TRANG 3: LỜI CHÚC (ĐÃ GẮN ẢNH 1) ================= -->
  <section id="message" class="page-section bg-dots-sky">
    <div class="letter-layout">
      <div class="photo-display-frame letter-photo-box">
        <div class="photo-inner">
          <img src="https://i.postimg.cc/m2wK8csG/1795049658649-1582624518448588765-g3643160542836226468-e085a437362b6379944008550615e5ff.jpg" alt="Kỷ niệm lớp học">
        </div>
        <span class="photo-caption">Tập thể lớp & Thầy Hiếu 💙</span>
      </div>

      <div class="letter-paper">
        <div class="letter-header-badge">Chúc Mừng 20/11! 💙</div>
        <div class="letter-body">
          Kính chúc Thầy HIẾU luôn mạnh khỏe và hạnh phúc.<br><br>
          Cảm ơn thầy đã tận tâm dìu dắt chúng em.<br>
          Chúc thầy luôn giữ vững ngọn lửa nhiệt huyết!<br><br>
          Trân trọng và biết ơn,<br>
          <span class="editable-name">9A2 mãi yêu quý và biết ơn thầy! ❤️</span>
        </div>
      </div>
    </div>

    <button class="back-arrow-btn" onclick="goToPage('surprise')">⬅ Chọn món quà khác</button>
  </section>

  <!-- ================= TRANG 4: HOA TƯƠI (ĐÃ GẮN ẢNH 2) ================= -->
  <section id="flowers" class="page-section bg-dots-sky">
    <div class="flowers-layout">
      <div>
        <svg width="250" height="290" viewBox="0 0 250 290" fill="none">
          <polygon points="45,115 205,115 155,260 95,260" fill="#dce7fc" stroke="#33529c" stroke-width="4"/>
          <polygon points="75,115 175,115 140,260 110,260" fill="#eef4ff" stroke="#33529c" stroke-width="3"/>
          <ellipse cx="75" cy="95" rx="22" ry="12" transform="rotate(-30 75 95)" fill="#8cc9a3" stroke="#33529c" stroke-width="3"/>
          <ellipse cx="175" cy="95" rx="22" ry="12" transform="rotate(30 175 95)" fill="#8cc9a3" stroke="#33529c" stroke-width="3"/>
          <circle cx="95" cy="95" r="26" fill="#f7b2c4" stroke="#33529c" stroke-width="3.5"/>
          <circle cx="155" cy="95" r="26" fill="#f7b2c4" stroke="#33529c" stroke-width="3.5"/>
          <circle cx="125" cy="65" r="28" fill="#ffd1de" stroke="#33529c" stroke-width="3.5"/>
          <circle cx="125" cy="112" r="27" fill="#f49ab2" stroke="#33529c" stroke-width="3.5"/>
          <path d="M125 210C102 195 88 212 105 222L125 210Z" fill="#f49ab2" stroke="#33529c" stroke-width="3"/>
          <path d="M125 210C148 195 162 212 145 222L125 210Z" fill="#f49ab2" stroke="#33529c" stroke-width="3"/>
          <circle cx="125" cy="210" r="7" fill="#33529c"/>
        </svg>
      </div>

      <div class="flower-message-card">
        🌸 Như những đóa hoa tươi thắm nhất, kính chúc Thầy HIẾU luôn rạng rỡ, bình an và gặt hái thật nhiều thành công trong sự nghiệp trồng người!
      </div>

      <div class="photo-display-frame flower-photo-box">
        <div class="photo-inner">
          <img src="https://i.postimg.cc/SxPTvC1P/1795100955160-1738685886417665290-g932709283410983386-6ed4d3d59a188743fdff8c82a4b5c211.jpg" alt="Khoảnh khắc 20/11">
        </div>
        <span class="photo-caption">Khoảnh khắc 20/11 🌸</span>
      </div>
    </div>

    <button class="back-arrow-btn" onclick="goToPage('surprise')">⬅ Chọn món quà khác</button>
  </section>

  <!-- ================= TRANG 5: TRI ÂN & LINK 9A2 BLOGSPOT ================= -->
  <section id="cake" class="page-section bg-stripes-retro">
    <div class="cake-stage">
      <div class="cake-top-row">
        <div class="memory-frames-col">
          <div class="photo-display-frame cake-photo-box">
            <div class="photo-inner">
              <img src="https://i.postimg.cc/CM4vVW64/1795100955145-1738685886417665290-g932709283410983386-d5498548bc9a837fb3152ffe0fc22d21.jpg" alt="Ảnh tập thể sân trường">
            </div>
            <span class="photo-caption">Tập thể sân trường ✨</span>
          </div>

          <div class="photo-display-frame cake-photo-box">
            <div class="photo-inner">
              <img src="https://i.postimg.cc/0QsCTfYX/1795100955123-1738685886417665290-g932709283410983386-9a77ec2f965184de71ad5886aab36d17.jpg" alt="Ảnh hoạt động lớp">
            </div>
            <span class="photo-caption">Kỷ niệm đáng nhớ 💙</span>
          </div>
        </div>

        <div style="text-align: center;">
          <svg width="240" height="220" viewBox="0 0 240 220" fill="none">
            <ellipse cx="120" cy="196" rx="102" ry="14" fill="#dce7fc" stroke="#33529c" stroke-width="3.5"/>
            <rect x="42" y="130" width="156" height="64" rx="12" fill="#8ca9e2" stroke="#33529c" stroke-width="4"/>
            <path d="M42 146Q62 162 81 146Q100 162 120 146Q140 162 159 146Q178 162 198 146" stroke="#ffffff" stroke-width="4" fill="none"/>
            <text x="120" y="178" text-anchor="middle" fill="#ffffff" font-family="Fredoka" font-size="16" font-weight="700">9A2 CHÚC MỪNG</text>
            <rect x="68" y="76" width="104" height="54" rx="10" fill="#f7d6e0" stroke="#33529c" stroke-width="4"/>
            <path d="M68 92Q85 106 102 92Q120 106 138 92Q155 106 172 92" stroke="#ffffff" stroke-width="3.5" fill="none"/>
            <rect x="92" y="46" width="8" height="30" rx="3" fill="#ffffff" stroke="#33529c" stroke-width="2.5"/>
            <rect x="116" y="42" width="8" height="34" rx="3" fill="#ffd166" stroke="#33529c" stroke-width="2.5"/>
            <rect x="140" y="46" width="8" height="30" rx="3" fill="#ffffff" stroke="#33529c" stroke-width="2.5"/>
            <circle cx="96" cy="38" r="5" fill="#ff9f1c"/>
            <circle cx="120" cy="34" r="6" fill="#ff9f1c"/>
            <circle cx="144" cy="38" r="5" fill="#ff9f1c"/>
          </svg>
        </div>
      </div>

      <!-- Khung nhúng Link Blogspot 9A2 của bạn -->
      <div class="blog-link-box">
        <div>
          <h3 style="font-family: 'Fredoka', sans-serif; color: var(--blue-dark); margin-bottom: 6px;">✨ Không Gian 9A2 Chúc Mừng Thầy Hiếu</h3>
          <p style="font-size: 0.95rem; color: #4763a6; margin-bottom: 12px;">Xem toàn bộ trang web lưu niệm đặc biệt của tập thể 9A2!</p>
          <a href="https://cuongbokit.blogspot.com/p/rain-lover.html?script=T%E1%BA%ACP%20TH%E1%BB%82%209A2%20ch%C3%BAc%20th%E1%BA%A7y%20Hi%E1%BA%BFu%7C%23countdown%203%7CCh%C3%BAc%20th%E1%BA%A7y%20Hi%E1%BA%BFu%20lu%C3%B4n%20m%E1%BA%A1nh%20kh%E1%BB%8Fe%20v%C3%A0%20h%E1%BA%A1nh%20ph%C3%BAc%7CC%E1%BA%A3m%20%C6%A1n%20th%E1%BA%A7y%20%C4%91%C3%A3%20t%E1%BA%ADn%20t%C3%A2m%20d%C3%ACu%20d%C3%BA%E1%BA%A5t%20ch%C3%BAng%20em%7CCh%C3%BAc%20th%E1%BA%A7y%20m%C3%A3i%20gi%E1%BB%AF%20v%E1%BB%AFng%20ng%E1%BB%8Dn%20l%E1%BB%ADa%20nhi%E1%BB%87t%20huy%E1%BA%BFt%7C9A2%20m%C3%A3i%20y%C3%AAu%20qu%C3%BD%20v%C3%A0%20bi%E1%BA%BFt%20%C6%A1n%20th%C3%A7y!%20%E2%9D%A4%EF%B8%8F" target="_blank" class="visit-blog-btn">Mở Trang Gốc 9A2 🚀</a>
        </div>
      </div>

      <div class="vinyl-box">
        <div class="vinyl-disc" id="vinyl-disc" onclick="toggleMusic()">
          <div class="vinyl-label" id="vinyl-text">Click Me 💙</div>
        </div>
        <div style="max-width: 320px; text-align: left;">
          <h3 style="font-family: 'Fredoka', sans-serif; color: var(--blue-dark); margin-bottom: 4px;">🎵 Giai Điệu Tri Ân</h3>
          <p style="font-size: 0.95rem; color: #4763a6;">Bấm vào đĩa than bên cạnh để bật/tắt bản nhạc piano chúc mừng Thầy Hiếu nhé!</p>
        </div>
      </div>
    </div>

    <button class="back-arrow-btn" onclick="goToPage('surprise')">⬅ Chọn món quà khác</button>
  </section>

<script>
  /* ================= HIỆU ỨNG HOA NỞ ================= */
  const canvas = document.getElementById('flower-canvas');
  const ctx = canvas.getContext('2d');
  let flowers = [];
  let bloomStarted = false;

  function resizeCanvas() {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
  }
  window.addEventListener('resize', resizeCanvas);
  resizeCanvas();

  const flowerPalettes = [
    { petals: '#f4a261', center: '#5c3a21', type: 'sunflower' },
    { petals: '#f28482', center: '#f6bd60', type: 'rose' },
    { petals: '#ffffff', center: '#f4c430', type: 'daisy' },
    { petals: '#90a8ed', center: '#f9e076', type: 'hydrangea' },
    { petals: '#f7cad0', center: '#e07a5f', type: 'rose' },
    { petals: '#e9c46a', center: '#6d4c3d', type: 'sunflower' },
    { petals: '#b892ff', center: '#ffe66d', type: 'daisy' }
  ];

  function drawSingleFlower(f) {
    ctx.save();
    ctx.translate(f.x, f.y);
    ctx.rotate(f.rotation);
    ctx.scale(f.currentScale, f.currentScale);

    ctx.fillStyle = '#7fb069';
    for (let l = 0; l < 3; l++) {
      ctx.save();
      ctx.rotate((l * Math.PI * 2) / 3 + 0.4);
      ctx.beginPath();
      ctx.ellipse(f.radius * 0.85, 0, f.radius * 0.45, f.radius * 0.22, 0, 0, Math.PI * 2);
      ctx.fill();
      ctx.restore();
    }

    const petalCount = f.type === 'sunflower' ? 14 : (f.type === 'daisy' ? 10 : 8);
    ctx.fillStyle = f.petals;
    for (let i = 0; i < petalCount; i++) {
      ctx.save();
      ctx.rotate((i * Math.PI * 2) / petalCount);
      ctx.beginPath();
      if (f.type === 'rose') {
        ctx.arc(f.radius * 0.42, 0, f.radius * 0.52, 0, Math.PI * 2);
      } else {
        ctx.ellipse(f.radius * 0.55, 0, f.radius * 0.48, f.radius * 0.24, 0, 0, Math.PI * 2);
      }
      ctx.fill();
      ctx.strokeStyle = 'rgba(255,255,255,0.4)';
      ctx.lineWidth = 1.5;
      ctx.stroke();
      ctx.restore();
    }

    ctx.beginPath();
    ctx.arc(0, 0, f.radius * 0.34, 0, Math.PI * 2);
    ctx.fillStyle = f.center;
    ctx.fill();

    ctx.restore();
  }

  function animateFlowers() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    for (let i = 0; i < flowers.length; i++) {
      const f = flowers[i];
      if (f.delay > 0) {
        f.delay--;
        continue;
      }
      if (f.currentScale < f.targetScale) {
        f.currentScale += (f.targetScale - f.currentScale) * 0.14;
      }
      f.rotation += f.rotSpeed;
      drawSingleFlower(f);
    }
    if (bloomStarted) {
      requestAnimationFrame(animateFlowers);
    }
  }

  function startFlowerBloom() {
    if (bloomStarted) return;
    bloomStarted = true;

    const env = document.getElementById('envelope-btn');
    env.style.transition = 'transform 0.4s ease, opacity 0.4s ease';
    env.style.transform = 'scale(0.5)';
    env.style.opacity = '0';

    const cx = canvas.width / 2;
    const cy = canvas.height / 2;
    const maxDist = Math.hypot(cx, cy);
    const totalFlowers = 210;

    for (let i = 0; i < totalFlowers; i++) {
      const progress = i / totalFlowers;
      const angle = i * 2.39996;
      const dist = Math.sqrt(progress) * (maxDist + 80);
      const palette = flowerPalettes[Math.floor(Math.random() * flowerPalettes.length)];

      flowers.push({
        x: cx + Math.cos(angle) * dist + (Math.random() - 0.5) * 40,
        y: cy + Math.sin(angle) * dist + (Math.random() - 0.5) * 40,
        radius: 36 + Math.random() * 28,
        currentScale: 0,
        targetScale: 0.9 + Math.random() * 0.45,
        rotation: Math.random() * Math.PI * 2,
        rotSpeed: (Math.random() - 0.5) * 0.008,
        delay: Math.floor(progress * 55),
        petals: palette.petals,
        center: palette.center,
        type: palette.type
      });
    }

    animateFlowers();

    setTimeout(() => {
      document.getElementById('tap-to-reveal').classList.add('show');
    }, 1600);
  }

  function enterMainSite() {
    const intro = document.getElementById('intro-screen');
    intro.classList.add('hidden');
    setTimeout(() => {
      bloomStarted = false;
    }, 850);
  }

  /* ================= ĐIỀU HƯỚNG ================= */
  function showPage(pageId, btnElement) {
    document.querySelectorAll('.page-section').forEach(sec => sec.classList.remove('active'));
    document.getElementById(pageId).classList.add('active');

    document.querySelectorAll('.nav-btn').forEach(btn => btn.classList.remove('active'));
    if (btnElement) btnElement.classList.add('active');
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }

  function goToPage(pageId) {
    const navMap = { home: 0, surprise: 1, message: 2, flowers: 3, cake: 4 };
    const btns = document.querySelectorAll('.nav-btn');
    showPage(pageId, btns[navMap[pageId]]);
  }

  /* ================= NHẠC PIANO ================= */
  let audioCtx = null;
  let isPlaying = false;
  let musicTimer = null;

  const melody = [
    { freq: 523.25, dur: 0.45 },
    { freq: 587.33, dur: 0.45 },
    { freq: 659.25, dur: 0.7 },
    { freq: 523.25, dur: 0.45 },
    { freq: 659.25, dur: 0.45 },
    { freq: 783.99, dur: 0.9 },
    { freq: 698.46, dur: 0.45 },
    { freq: 659.25, dur: 0.45 },
    { freq: 587.33, dur: 0.9 },
    { freq: 523.25, dur: 0.45 },
    { freq: 587.33, dur: 0.45 },
    { freq: 659.25, dur: 0.45 },
    { freq: 523.25, dur: 1.0 }
  ];

  function playNote(freq, duration) {
    if (!audioCtx) audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    const osc = audioCtx.createOscillator();
    const gain = audioCtx.createGain();
    osc.type = 'sine';
    osc.frequency.setValueAtTime(freq, audioCtx.currentTime);

    gain.gain.setValueAtTime(0.001, audioCtx.currentTime);
    gain.gain.exponentialRampToValueAtTime(0.15, audioCtx.currentTime + 0.05);
    gain.gain.exponentialRampToValueAtTime(0.0001, audioCtx.currentTime + duration);

    osc.connect(gain);
    gain.connect(audioCtx.destination);
    osc.start();
    osc.stop(audioCtx.currentTime + duration);
  }

  function toggleMusic() {
    const disc = document.getElementById('vinyl-disc');
    const label = document.getElementById('vinyl-text');

    if (isPlaying) {
      isPlaying = false;
      clearTimeout(musicTimer);
      disc.classList.remove('playing');
      label.textContent = 'Click Me 💙';
      return;
    }

    isPlaying = true;
    disc.classList.add('playing');
    label.textContent = 'Đang phát 🎶';

    let noteIndex = 0;
    function loopMelody() {
      if (!isPlaying) return;
      const note = melody[noteIndex];
      playNote(note.freq, note.dur);
      noteIndex = (noteIndex + 1) % melody.length;
      musicTimer = setTimeout(loopMelody, note.dur * 1000);
    }
    loopMelody();
  }
</script>
</body>
</html>
