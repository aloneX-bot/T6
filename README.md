
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#ffffff">
<title>YourBrand.ai — Create Beautiful Ebooks</title>

<link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700;800&family=Playfair+Display:wght@500;600;700&display=swap" rel="stylesheet">

<style>
:root{
 --orange:#f47761;
 --pink:#fac5bb;
 --brown:#382d29;
 --muted:#827a76;
 --cream:#faf7f3;
 --border:#eae6e1;
}
*{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{font-family:'DM Sans',sans-serif;color:var(--brown);background:white}
button{font:inherit;cursor:pointer}
a{text-decoration:none;color:inherit}
.container{width:min(1100px,92%);margin:auto}

/* HEADER */
header{
 height:70px;background:white;
 position:sticky;top:0;z-index:50;
 border-bottom:1px solid #f1efec;
}
.nav{
 height:100%;display:flex;
 align-items:center;justify-content:space-between;
}
.logo{
 font-size:21px;font-weight:700;
 letter-spacing:-.7px;color:var(--brown);
}
.logo span{color:var(--orange)}
.menu-btn{
 background:none;border:0;
 font-size:27px;color:var(--brown);
 padding:5px 10px;
}
.menu-panel{
 display:none;position:absolute;top:70px;
 right:4%;width:190px;background:white;
 padding:20px;border:1px solid var(--border);
 border-radius:10px;box-shadow:0 10px 30px #00000012;
}
.menu-panel.open{display:flex;flex-direction:column;gap:17px}
.menu-panel a{font-size:13px}

/* HERO */
.hero{
 padding:30px 0 65px;text-align:center;
 background:radial-gradient(ellipse at 50% 25%,#fff9f7,white 70%);
}
.social-proof{
 display:inline-flex;align-items:center;gap:12px;
 border:1px solid #f1ded9;border-radius:40px;
 padding:11px 19px;color:#a95645;
 font-size:14px;font-weight:700;margin-bottom:40px;
}
.proof-dot{
 width:12px;height:12px;border-radius:50%;
 background:var(--orange);
 box-shadow:0 0 0 5px #fce5df;
}
.hero h1{
 font-size:clamp(43px,7vw,75px);
 font-weight:800;letter-spacing:-2.5px;
 line-height:1.13;margin-bottom:40px;
}
.hero h1 span{color:var(--orange)}
.hero-description{
 max-width:740px;margin:auto;
 font-size:clamp(16px,2.5vw,27px);
 line-height:1.75;color:var(--muted);
}
.prompt-wrap{max-width:850px;margin:45px auto 20px}
.prompt-box{
 position:relative;min-height:260px;
 border:1.5px solid #e7e3df;border-radius:25px;
 background:white;box-shadow:0 15px 45px #00000008;
}
.prompt-box textarea{
 width:100%;height:205px;padding:28px 30px 65px;
 border:0;outline:none;resize:none;
 background:transparent;border-radius:25px;
 font-family:inherit;font-size:21px;line-height:1.6;
}
.prompt-box textarea::placeholder{color:#c1bfbd}
.send-btn{
 position:absolute;right:23px;bottom:20px;
 height:72px;width:72px;border:0;
 border-radius:50%;background:var(--pink);
 color:white;font-size:37px;transition:.2s;
}
.send-btn:hover{background:var(--orange);transform:translateY(-3px)}
.suggestions{
 display:flex;justify-content:center;
 flex-wrap:wrap;gap:12px;margin-top:20px;
}
.suggestion{
 padding:11px 20px;border:1px solid #e8e4df;
 border-radius:30px;background:white;
 color:#706761;font-size:14px;
}
.suggestion:first-child,.suggestion:hover{
 border-color:#f1c6bc;color:#a95848;background:#fffaf8;
}
.hero-note{
 margin-top:55px;color:#aaa39e;
 font-size:clamp(14px,2.3vw,21px);line-height:1.6;
}
.see-how{
 display:inline-block;margin-top:20px;
 color:#958d87;font-size:18px;font-weight:700;
}

/* PLATFORMS */
.platforms{padding:55px 0 100px;text-align:center}
.platform-title{
 color:#aaa39f;font-size:16px;
 letter-spacing:2px;font-weight:600;margin-bottom:38px;
}
.platform-grid{
 display:flex;justify-content:center;
 align-items:center;flex-wrap:wrap;gap:38px;
 max-width:900px;margin:auto;
}
.platform{
 width:65px;height:60px;
 display:flex;align-items:center;justify-content:center;
 filter:grayscale(1);opacity:.65;transition:.2s;
}
.platform:hover{filter:none;opacity:1;transform:translateY(-3px)}
.platform img{max-width:52px;max-height:43px;object-fit:contain}

/* SHOWCASE */
.showcase{
 background:var(--cream);padding:85px 0 90px;
 text-align:center;
}
.section-tag{
 display:inline-block;background:white;
 border:1px solid #f0e5df;border-radius:40px;
 padding:12px 23px;color:#a65b4a;
 font-size:14px;font-weight:700;margin-bottom:30px;
}
.section-title{
 font-size:clamp(35px,5vw,53px);
 line-height:1.2;letter-spacing:-1.5px;
 font-weight:800;color:var(--brown);
 max-width:850px;margin:0 auto 22px;
}
.section-description{
 max-width:800px;margin:auto;
 color:#827873;font-size:clamp(15px,2.2vw,23px);
 line-height:1.8;
}

/* BOOK VIEWER */
.book-viewer{
 max-width:850px;margin:48px auto 0;
}
.book-tabs{
 display:flex;justify-content:center;
 gap:10px;flex-wrap:wrap;margin-bottom:28px;
}
.book-tab{
 padding:11px 19px;border:1px solid #e7ddd6;
 border-radius:30px;background:white;
 color:#71645e;font-size:13px;font-weight:600;
}
.book-tab.active{
 background:var(--orange);color:white;border-color:var(--orange);
}
.book-stage{
 min-height:400px;display:flex;
 align-items:center;justify-content:center;
}
.open-book{
 width:min(100%,650px);
 display:grid;grid-template-columns:1fr 1fr;
 gap:5px;
 perspective:1000px;
}
.book-page{
 min-height:350px;background:white;
 padding:32px 27px;position:relative;
 box-shadow:0 8px 22px #0000000c;
 text-align:left;overflow:hidden;
}
.book-page.left-page{border-radius:9px 0 0 9px}
.book-page.right-page{border-radius:0 9px 9px 0}
.page-inner{
 height:100%;display:flex;flex-direction:column;
 justify-content:space-between;
}
.cover-page{
 display:flex;flex-direction:column;
 align-items:center;justify-content:space-between;
 text-align:center;color:white;min-height:285px;
}
.cover-page .cover-label{
 font-size:9px;letter-spacing:2px;
}
.cover-page h2{
 font-family:'Playfair Display',serif;
 font-size:clamp(24px,4vw,35px);
 line-height:1.2;
}
.cover-art{font-size:65px}
.cover-author{font-size:10px;letter-spacing:2px}
.page-heading{
 font-family:'Playfair Display',serif;
 font-size:21px;line-height:1.3;
 margin-bottom:17px;
}
.page-text{
 font-family:'Playfair Display',serif;
 font-size:12px;line-height:1.9;
 color:#6d625c;white-space:pre-line;
}
.page-number{
 font-size:10px;color:#a39a93;
 text-align:center;margin-top:20px;
}
.page-ornament{
 height:3px;width:38px;background:var(--orange);
 margin-bottom:17px;
}
.page-nav{
 display:flex;align-items:center;
 justify-content:center;gap:22px;margin-top:25px;
}
.circle-btn{
 width:47px;height:47px;border-radius:50%;
 border:1px solid #e4dcd5;background:white;
 color:var(--brown);font-size:22px;
 display:grid;place-items:center;transition:.2s;
}
.circle-btn:hover{background:var(--orange);color:white;border-color:var(--orange)}
.page-counter{
 font-size:14px;color:#70645d;
 font-weight:600;min-width:75px;
}
.book-information{margin-top:25px}
.book-information h3{
 font-family:'Playfair Display',serif;
 font-size:24px;margin-bottom:7px;
}
.book-information p{font-size:13px;color:#938981}
.book-dots{
 display:flex;justify-content:center;gap:6px;
 margin-top:17px;
}
.book-dot{
 height:6px;width:6px;border-radius:50%;
 background:#d8cec6;
}
.book-dot.active{background:var(--orange);width:19px;border-radius:10px}

/* FEATURES */
.features-section{padding:90px 0}
.section-head{text-align:center;margin-bottom:48px}
.section-head p{color:var(--muted);font-size:14px;margin-top:13px}
.features{
 display:grid;grid-template-columns:repeat(3,1fr);gap:18px;
}
.feature{
 padding:27px;border:1px solid var(--border);
 border-radius:13px;background:white;
 transition:.2s;
}
.feature:hover{transform:translateY(-4px);box-shadow:0 10px 25px #00000008}
.feature-icon{
 width:45px;height:45px;border-radius:12px;
 background:#fff0ec;display:grid;place-items:center;
 font-size:22px;margin-bottom:17px;
}
.feature h3{font-size:18px;margin-bottom:10px}
.feature p{font-size:13px;line-height:1.8;color:var(--muted)}

/* HOW */
.how{background:#fff8f5;padding:85px 0}
.steps{display:grid;grid-template-columns:repeat(3,1fr);gap:25px}
.step{text-align:center;padding:20px}
.step-number{font-size:43px;color:var(--orange);font-weight:800}
.step h3{font-size:20px;margin:15px 0 10px}
.step p{font-size:13px;line-height:1.8;color:var(--muted)}

/* PRICING */
.pricing{padding:90px 0}
.price-card{
 max-width:430px;margin:auto;padding:32px;
 border:1px solid var(--border);border-radius:15px;
}
.price{font-size:50px;font-weight:800;margin:18px 0}
.price small{font-size:13px;color:var(--muted)}
.price-card ul{list-style:none;margin:25px 0}
.price-card li{padding:10px 0;font-size:14px}
.price-card li:before{content:"✓";color:var(--orange);margin-right:10px}
.btn-primary{
 background:var(--orange);color:white;
 border:0;border-radius:8px;padding:13px 20px;
 font-size:13px;font-weight:700;
}
.price-card button{width:100%}

/* FAQ */
.faq-section{background:var(--cream);padding:85px 0}
.faq{max-width:750px;margin:auto}
.faq-item{padding:20px 0;border-bottom:1px solid #e5ded7}
.faq-question{
 display:flex;justify-content:space-between;
 cursor:pointer;font-size:14px;font-weight:700;
}
.faq-answer{
 display:none;color:var(--muted);
 font-size:13px;line-height:1.8;padding-top:14px;
}
.faq-item.active .faq-answer{display:block}

/* CTA AND FOOTER */
.cta{padding:75px 0;text-align:center}
.cta-inner{
 background:#382d29;color:white;
 border-radius:17px;padding:60px 20px;
}
.cta-inner h2{font-size:clamp(30px,5vw,45px);margin-bottom:15px}
.cta-inner p{color:#d9cfca;margin-bottom:22px;font-size:14px}
footer{border-top:1px solid var(--border);padding:28px 0}
.footer{
 display:flex;justify-content:space-between;
 align-items:center;flex-wrap:wrap;gap:15px;
}
.footer p,.footer-links{font-size:12px;color:var(--muted)}
.footer-links{display:flex;gap:20px}

/* GENERATOR */
.generator{
 position:fixed;inset:0;background:#201c1af5;
 z-index:100;display:none;overflow-y:auto;padding:18px;
}
.generator.open{display:block}
.gen-inner{max-width:950px;margin:auto;color:white}
.gen-top{
 display:flex;justify-content:space-between;
 align-items:center;margin-bottom:25px;
}
.gen-top button{
 background:#ffffff20;color:white;
 border:0;padding:11px 17px;border-radius:8px;
}
.gen-grid{display:grid;grid-template-columns:330px 1fr;gap:20px}
.gen-panel{background:white;color:var(--brown);padding:24px;border-radius:12px}
.gen-panel h2{font-size:23px;margin-bottom:10px}
.gen-panel>p{font-size:12px;color:var(--muted);margin-bottom:20px}
.field{margin-bottom:16px}
.field label{display:block;font-size:11px;font-weight:700;margin-bottom:8px}
.field input,.field textarea,.field select{
 width:100%;padding:12px;border:1px solid var(--border);
 border-radius:7px;font:inherit;font-size:12px;
}
.field textarea{height:90px;resize:vertical}
.gen-panel .btn-primary{width:100%}
.gen-preview{background:#f7f4f0;color:var(--brown);padding:20px;border-radius:12px}
.gen-preview-top{display:flex;justify-content:space-between;font-size:12px;margin-bottom:15px}
.result-cover{
 min-height:220px;background:linear-gradient(145deg,#f47761,#9c4c43);
 display:flex;flex-direction:column;align-items:center;
 justify-content:center;color:white;text-align:center;padding:25px;
}
.result-cover h2{font-family:'Playfair Display',serif;font-size:28px;margin:18px 0}
.result-content{background:white;padding:23px}
.result-content h3{margin:15px 0}
.result-content p{font-size:12px;line-height:1.8;color:var(--muted)}
.chapter-nav{display:flex;flex-wrap:wrap;gap:6px;margin:13px 0}
.chapter-nav button{
 padding:8px;border:1px solid var(--border);
 background:white;border-radius:5px;font-size:10px;
}
.chapter-nav button.selected{background:var(--brown);color:white}
.result-content textarea{
 width:100%;height:145px;padding:12px;
 border:1px solid var(--border);font:inherit;font-size:12px;
}
.result-actions{display:flex;gap:8px;flex-wrap:wrap;margin-top:12px}
.status{font-size:11px;color:#60856a;margin-top:12px}

@media(max-width:750px){
 .features{grid-template-columns:repeat(2,1fr)}
 .gen-grid{grid-template-columns:1fr}
}
@media(max-width:550px){
 header{height:65px}
 .logo{font-size:19px}
 .menu-panel{top:65px}
 .hero{padding:25px 0 45px}
 .social-proof{font-size:12px;padding:10px 13px;margin-bottom:38px}
 .hero h1{font-size:46px;letter-spacing:-1.8px;margin-bottom:38px}
 .hero-description{font-size:17px}
 .prompt-wrap{margin-top:40px}
 .prompt-box{min-height:250px}
 .prompt-box textarea{height:200px;padding:25px;font-size:19px}
 .send-btn{height:65px;width:65px}
 .suggestions{flex-direction:column;align-items:center}
 .suggestion{font-size:13px;padding:11px 17px}
 .hero-note{font-size:15px;margin-top:50px}
 .platforms{padding:45px 0 80px}
 .platform-grid{gap:20px 13px}
 .platform{width:55px;height:50px}
 .platform img{max-width:42px;max-height:36px}
 .showcase{padding:70px 0}
 .section-title{font-size:36px;letter-spacing:-1px}
 .section-description{font-size:16px}
 .book-stage{min-height:300px}
 .book-page{min-height:300px;padding:18px 13px}
 .cover-page{min-height:260px}
 .cover-page h2{font-size:23px}
 .cover-art{font-size:45px}
 .page-heading{font-size:17px}
 .page-text{font-size:10px;line-height:1.7}
 .book-information h3{font-size:21px}
 .features-section,.pricing,.faq-section,.how{padding:70px 0}
 .features,.steps{grid-template-columns:1fr}
 .cta-inner{padding:45px 17px}
 .footer{flex-direction:column;align-items:flex-start}
}
</style>
</head>

<body>

<!-- SIMPLE HEADER -->
<header>
 <div class="container nav">
  <a href="#" class="logo">YourBrand<span>.ai</span></a>

  <button class="menu-btn" onclick="toggleMenu()" aria-label="Open menu">☰</button>

  <nav class="menu-panel" id="menuPanel">
   <a href="#showcase">Book examples</a>
   <a href="#features">Features</a>
   <a href="#how">How it works</a>
   <a href="#pricing">Pricing</a>
   <a href="#faq">FAQ</a>
  </nav>
 </div>
</header>

<!-- HERO -->
<section class="hero">
 <div class="container">

  <div class="social-proof">
   <span class="proof-dot"></span>
   Loved by 12,000+ creators publishing with AI
  </div>

  <h1>
   Write it once.<br>
   <span>Let it earn<br>forever.</span>
  </h1>

  <p class="hero-description">
   Just tell Booker what you know. Watch it write every chapter and design your cover, building your finished ebook live in front of you.
  </p>

  <div class="prompt-wrap">
   <div class="prompt-box">
    <textarea id="mainPrompt" placeholder="Tell Booker what your book is about..."></textarea>
    <button class="send-btn" onclick="startBook()">↑</button>
   </div>

   <div class="suggestions">
    <button class="suggestion" onclick="useSuggestion(this)">A meal-prep guide for busy parents</button>
    <button class="suggestion" onclick="useSuggestion(this)">Side-hustle 101 for complete beginners</button>
    <button class="suggestion" onclick="useSuggestion(this)">A productivity system that actually sticks</button>
   </div>
  </div>

  <div class="hero-note">
   No credit card to start · cancel anytime · plans from $29/mo
  </div>

  <a href="#how" class="see-how">See how it works ↓</a>

 </div>
</section>

<!-- PUBLISHING PLATFORMS -->
<section class="platforms">
 <div class="container">
  <div class="platform-title">PUBLISH AND SELL ON</div>

  <div class="platform-grid">

   <a class="platform" href="https://kdp.amazon.com/" target="_blank">
    <img src="https://cdn.simpleicons.org/amazonkindle/777777" alt="Amazon Kindle">
   </a>

   <a class="platform" href="https://books.apple.com/" target="_blank">
    <img src="https://cdn.simpleicons.org/applebooks/777777" alt="Apple Books">
   </a>

   <a class="platform" href="https://www.etsy.com/" target="_blank">
    <img src="https://cdn.simpleicons.org/etsy/777777" alt="Etsy">
   </a>

   <a class="platform" href="https://gumroad.com/" target="_blank">
    <img src="https://cdn.simpleicons.org/gumroad/777777" alt="Gumroad">
   </a>

   <a class="platform" href="https://www.instagram.com/" target="_blank">
    <img src="https://cdn.simpleicons.org/instagram/777777" alt="Instagram">
   </a>

   <a class="platform" href="https://www.tiktok.com/" target="_blank">
    <img src="https://cdn.simpleicons.org/tiktok/777777" alt="TikTok">
   </a>

   <a class="platform" href="https://www.facebook.com/" target="_blank">
    <img src="https://cdn.simpleicons.org/facebook/777777" alt="Facebook">
   </a>

   <a class="platform" href="https://www.shopify.com/" target="_blank">
    <img src="https://cdn.simpleicons.org/shopify/777777" alt="Shopify">
   </a>

  </div>
 </div>
</section>

<!-- INTERACTIVE BOOK SHOWCASE -->
<section class="showcase" id="showcase">
 <div class="container">

  <div class="section-tag">FLIP THROUGH A REAL BOOK</div>

  <h2 class="section-title">See exactly what you'll create</h2>

  <p class="section-description">
   These are real books made with YourBrand.ai. One is a polished ebook which can sell many times. Tap the arrows to flip through its first pages.
  </p>

  <div class="book-viewer">

   <div class="book-tabs">
    <button class="book-tab active" id="tab0" onclick="changeBook(0)">
     Healthy Living Ebook
    </button>
    <button class="book-tab" id="tab1" onclick="changeBook(1)">
     Parenting Guide
    </button>
   </div>

   <div class="book-stage">
    <div class="open-book" id="openBook">

     <div class="book-page left-page" id="leftPage"></div>
     <div class="book-page right-page" id="rightPage"></div>

    </div>
   </div>

   <div class="page-nav">
    <button class="circle-btn" onclick="previousPage()" aria-label="Previous page">←</button>
    <span class="page-counter" id="pageCounter">1 of 12</span>
    <button class="circle-btn" onclick="nextPage()" aria-label="Next page">→</button>
   </div>

   <div class="book-dots" id="bookDots"></div>

   <div class="book-information">
    <h3 id="bookName">Healthy Living: Small Habits, Big Changes</h3>
    <p id="bookPageInfo">Ebook cover + 11 pages · Digital Ebook</p>
   </div>

  </div>

 </div>
</section>

<!-- FEATURES -->
<section class="features-section" id="features">
 <div class="container">

  <div class="section-head">
   <div class="section-tag">YOUR COMPLETE BOOK STUDIO</div>
   <h2 class="section-title">Everything you need to create your next ebook.</h2>
   <p>One workspace. Your ideas. Your finished digital products.</p>
  </div>

  <div class="features">

   <div class="feature">
    <div class="feature-icon">✍️</div>
    <h3>AI Book Writing</h3>
    <p>Transform your ideas into organized book outlines and readable chapters.</p>
   </div>

   <div class="feature">
    <div class="feature-icon">🎨</div>
    <h3>AI Cover Design</h3>
    <p>Create attractive cover concepts for your digital books.</p>
   </div>

   <div class="feature">
    <div class="feature-icon">📚</div>
    <h3>Book Structures</h3>
    <p>Organize your ebooks into sections and chapters.</p>
   </div>

   <div class="feature">
    <div class="feature-icon">📝</div>
    <h3>Chapter Editor</h3>
    <p>Edit your manuscript and customize your writing.</p>
   </div>

   <div class="feature">
    <div class="feature-icon">📄</div>
    <h3>Book Export</h3>
    <p>Prepare your book for digital publishing.</p>
   </div>

   <div class="feature">
    <div class="feature-icon">🚀</div>
    <h3>Publishing Workflow</h3>
    <p>Bring your book idea from the first prompt to a finished manuscript.</p>
   </div>

  </div>
 </div>
</section>

<!-- HOW IT WORKS -->
<section class="how" id="how">
 <div class="container">
  <div class="section-head">
   <div class="section-tag">HOW IT WORKS</div>
   <h2 class="section-title">Your knowledge deserves to become a book.</h2>
  </div>

  <div class="steps">
   <div class="step">
    <div class="step-number">01</div>
    <h3>Tell Booker your idea</h3>
    <p>Enter a topic or concept you want to turn into a book.</p>
   </div>

   <div class="step">
    <div class="step-number">02</div>
    <h3>Create your manuscript</h3>
    <p>Develop your outline and chapters in one workspace.</p>
   </div>

   <div class="step">
    <div class="step-number">03</div>
    <h3>Publish your ebook</h3>
    <p>Review your work and prepare it for publishing.</p>
   </div>
  </div>
 </div>
</section>

<!-- PRICING -->
<section class="pricing" id="pricing">
 <div class="container">
  <div class="section-head">
   <div class="section-tag">SIMPLE PRICING</div>
   <h2 class="section-title">Start creating today.</h2>
  </div>

  <div class="price-card">
   <h3>Creator Plan</h3>
   <div class="price">$29<small> / month</small></div>
   <p style="font-size:12px;color:#888">Example pricing. Payments are not connected.</p>

   <ul>
    <li>Book creation workspace</li>
    <li>Book outline tools</li>
    <li>Chapter editing</li>
    <li>Cover design workspace</li>
    <li>Manuscript preview</li>
    <li>Publishing preparation</li>
   </ul>

   <button class="btn-primary" onclick="openGenerator()">Start creating →</button>
  </div>
 </div>
</section>

<!-- FAQ -->
<section class="faq-section" id="faq">
 <div class="container">
  <div class="section-head">
   <div class="section-tag">FAQ</div>
   <h2 class="section-title">Frequently asked questions.</h2>
  </div>

  <div class="faq">

   <div class="faq-item">
    <div class="faq-question" onclick="toggleFaq(this)">
     What is Booker? <span>+</span>
    </div>
    <div class="faq-answer">Booker is the AI ebook creation assistant concept, designed to help users turn ideas into organized books.</div>
   </div>

   <div class="faq-item">
    <div class="faq-question" onclick="toggleFaq(this)">
     Do I need writing experience? <span>+</span>
    </div>
    <div class="faq-answer">No. The planned workflow is designed for beginners as well as experienced writers.</div>
   </div>

   <div class="faq-item">
    <div class="faq-question" onclick="toggleFaq(this)">
     Can I edit my book? <span>+</span>
    </div>
    <div class="faq-answer">Yes. The demonstration workspace includes editable chapter text.</div>
   </div>

   <div class="faq-item">
    <div class="faq-question" onclick="toggleFaq(this)">
     Does it use real AI? <span>+</span>
    </div>
    <div class="faq-answer">This frontend version uses demonstration content. Real AI generation requires a secure backend integration.</div>
   </div>

   <div class="faq-item">
    <div class="faq-question" onclick="toggleFaq(this)">
     Can I sell my ebooks? <span>+</span>
    </div>
    <div class="faq-answer">The platform is designed around ebook publishing. Actual sales depend on your publishing platform and its policies.</div>
   </div>

  </div>
 </div>
</section>

<!-- CTA -->
<section class="cta">
 <div class="container">
  <div class="cta-inner">
   <h2>Write it once. Let it earn forever.</h2>
   <p>Your next ebook starts with a single idea.</p>
   <button class="btn-primary" onclick="openGenerator()">Create your first book →</button>
  </div>
 </div>
</section>

<footer>
 <div class="container footer">
  <a href="#" class="logo">YourBrand<span>.ai</span></a>
  <div class="footer-links">
   <a href="#features">Features</a>
   <a href="#pricing">Pricing</a>
   <a href="#faq">FAQ</a>
  </div>
  <p>© 2026 YourBrand.ai</p>
 </div>
</footer>

<!-- BOOK GENERATOR -->
<div class="generator" id="generator">
 <div class="gen-inner">

  <div class="gen-top">
   <h2>Booker — Book Studio</h2>
   <button onclick="closeGenerator()">✕ Close</button>
  </div>

  <div class="gen-grid">
   <div class="gen-panel">
    <h2>Create your book</h2>
    <p>Customize your book details and create a sample preview.</p>

    <div class="field">
     <label>BOOK TOPIC</label>
     <textarea id="bookTopic" placeholder="What is your book about?"></textarea>
    </div>

    <div class="field">
     <label>TARGET AUDIENCE</label>
     <input id="bookAudience" placeholder="Example: Beginners">
    </div>

    <div class="field">
     <label>BOOK TYPE</label>
     <select id="bookType">
      <option>Educational Ebook</option>
      <option>Practical Guide</option>
      <option>Business Ebook</option>
      <option>Self Improvement</option>
      <option>Workbook</option>
     </select>
    </div>

    <button class="btn-primary" onclick="generateBook()">Generate book preview →</button>
    <div class="status" id="genStatus"></div>
   </div>

   <div class="gen-preview">
    <div class="gen-preview-top">
     <b>YOUR BOOK PREVIEW</b>
     <span id="previewStatus">Waiting for your idea</span>
    </div>

    <div id="bookResult" style="background:white;min-height:350px;padding:30px;text-align:center">
     <div style="font-size:50px;margin-top:90px">📖</div>
     <h3>Your book starts here.</h3>
    </div>
   </div>
  </div>
 </div>
</div>

<script>

/* MENU */
function toggleMenu(){
 document.getElementById('menuPanel').classList.toggle('open');
}

/* HERO */
function useSuggestion(button){
 document.getElementById('mainPrompt').value=button.textContent.trim();
}

function openGenerator(topic=''){
 document.getElementById('generator').classList.add('open');
 document.body.style.overflow='hidden';
 if(topic)document.getElementById('bookTopic').value=topic;
}

function closeGenerator(){
 document.getElementById('generator').classList.remove('open');
 document.body.style.overflow='';
}

function startBook(){
 const topic=document.getElementById('mainPrompt').value.trim();
 if(topic.length<5){
  document.getElementById('mainPrompt').focus();
  return;
 }
 openGenerator(topic);
 generateBook();
}

document.getElementById('mainPrompt').addEventListener('keydown',function(e){
 if(e.key==='Enter'&&!e.shiftKey){
  e.preventDefault();
  startBook();
 }
});

/* BOOK DATA: 12 PAGES EACH */
const books=[
 {
  title:'Healthy Living: Small Habits, Big Changes',
  description:'Ebook cover + 11 pages · Digital Ebook',
  cover:'#e9a58b',
  dark:'#a95042',
  icon:'🌿',
  label:'YOUR GUIDE TO BETTER LIVING',
  author:'A PRACTICAL GUIDE',
  pages:[
   {heading:'Welcome to a Healthier Life',text:'Small changes can make a meaningful difference over time. This book explores simple ways to build everyday habits that support a balanced lifestyle.\n\nThe goal is not perfection. It is consistency, curiosity and progress.'},
   {heading:'Chapter 1 — Start Small',text:'A lasting routine often begins with a small, manageable action.\n\nChoose one habit that fits your everyday schedule. Make it easy to repeat and give yourself time to become comfortable with it.'},
   {heading:'Chapter 2 — Building a Routine',text:'A routine works best when it fits naturally into your day.\n\nConnect a new habit to something you already do. Keep your plan realistic and adjust it when your circumstances change.'},
   {heading:'Chapter 3 — Everyday Nutrition',text:'A balanced eating pattern can include a variety of fruits, vegetables, grains, proteins and other foods.\n\nExplore different ingredients, enjoy variety and learn simple meal preparation techniques.'},
   {heading:'Chapter 4 — Meal Planning',text:'Planning meals can make busy days easier.\n\nCreate a simple weekly menu, prepare a shopping list and organize ingredients in advance. Leave room for flexibility.'},
   {heading:'Chapter 5 — Staying Active',text:'Movement can be part of ordinary daily life.\n\nFind enjoyable activities that suit your interests and abilities. Consistency matters more than complicated routines.'},
   {heading:'Chapter 6 — Rest and Recovery',text:'Rest is an important part of everyday wellbeing.\n\nBuild a comfortable evening routine and make space for regular breaks throughout your day.'},
   {heading:'Chapter 7 — Managing Busy Days',text:'Busy schedules can make routines challenging.\n\nPrepare simple alternatives for days when your normal plan is difficult. Small actions can help maintain continuity.'},
   {heading:'Chapter 8 — Creating Your Own Plan',text:'Choose the ideas that work best for your lifestyle.\n\nWrite down a few realistic habits, identify possible obstacles and decide how you will review your progress.'},
   {heading:'A Weekly Habit Checklist',text:'My weekly planning checklist:\n\n□ Plan meals\n□ Organize daily activities\n□ Make time for enjoyable movement\n□ Review personal goals\n□ Prepare for the week ahead'},
   {heading:'Your Next Chapter',text:'A healthier routine is something you can continue developing.\n\nStay flexible, keep learning and celebrate the useful habits you build along the way.'}
  ]
 },
 {
  title:'The Complete Parenting Guide for Busy Parents',
  description:'Ebook cover + 11 pages · Family & Parenting Guide',
  cover:'#63816d',
  dark:'#294b3b',
  icon:'🏡',
  label:'A GUIDE FOR MODERN FAMILIES',
  author:'PARENTING WITH CONFIDENCE',
  pages:[
   {heading:'Welcome, Parents',text:'Family life can be rewarding, busy and full of unexpected moments.\n\nThis guide explores practical ideas for creating routines, communicating with children and organizing everyday family life.'},
   {heading:'Chapter 1 — Understanding Your Child',text:'Every child has individual interests, experiences and needs.\n\nPay attention to their questions, listen carefully and make time for meaningful conversations.'},
   {heading:'Chapter 2 — Morning Routines',text:'A predictable morning can make the beginning of the day easier.\n\nPrepare school items in advance, allow enough time and keep everyday tasks simple.'},
   {heading:'Chapter 3 — Healthy Family Meals',text:'Family meals can be a useful opportunity to spend time together.\n\nExplore simple recipes, invite children to participate in age-appropriate tasks and encourage variety.'},
   {heading:'Chapter 4 — Learning Through Play',text:'Play offers opportunities for exploration and creativity.\n\nBooks, puzzles, outdoor activities and imaginative games can all become part of everyday learning.'},
   {heading:'Chapter 5 — Communication',text:'Good communication begins with listening.\n\nGive children time to express their thoughts, ask open questions and respond with patience.'},
   {heading:'Chapter 6 — Screen Time and Technology',text:'Technology is part of modern family life.\n\nCreate clear household expectations, discuss online safety and make time for offline activities.'},
   {heading:'Chapter 7 — Family Organization',text:'Shared calendars and simple lists can help organize family responsibilities.\n\nChoose a system that everyone can understand and use consistently.'},
   {heading:'Chapter 8 — Quality Family Time',text:'Meaningful family time does not need to involve elaborate plans.\n\nReading together, cooking, walking or sharing a conversation can create valuable moments.'},
   {heading:'The Family Weekly Planner',text:'Our weekly family planner:\n\n□ School and activity schedule\n□ Meal planning\n□ Family activities\n□ Household responsibilities\n□ Time for reading and learning'},
   {heading:'A Note to Parents',text:'There is no single perfect way to organize family life.\n\nUse the ideas that suit your circumstances, remain flexible and seek qualified professional guidance whenever a specific parenting or child-development concern requires it.'}
  ]
 }
];

let selectedBook=0;
let currentPage=0;
const TOTAL_PAGES=12;

/* BOOK VIEWER */
function changeBook(index){
 selectedBook=index;
 currentPage=0;

 document.getElementById('tab0').classList.toggle('active',index===0);
 document.getElementById('tab1').classList.toggle('active',index===1);

 renderBookViewer();
}

function makeCover(){
 const book=books[selectedBook];

 return `
 <div class="cover-page">
  <div class="cover-label">${book.label}</div>
  <div>
   <div class="cover-art">${book.icon}</div>
   <h2>${book.title}</h2>
  </div>
  <div class="cover-author">${book.author}</div>
 </div>`;
}

function makePage(page,index){
 return `
 <div class="page-inner">
  <div>
   <div class="page-ornament"></div>
   <h3 class="page-heading">${page.heading}</h3>
   <p class="page-text">${page.text}</p>
  </div>
  <div class="page-number">${index+1}</div>
 </div>`;
}

function renderBookViewer(){
 const book=books[selectedBook];

 const left=document.getElementById('leftPage');
 const right=document.getElementById('rightPage');

 if(currentPage===0){
  left.style.background=book.dark;
  left.style.color='white';
  left.innerHTML=makeCover();

  right.style.background='white';
  right.style.color='#382d29';
  right.innerHTML=makePage({
   heading:'A Note to the Reader',
   text:'Welcome to this book. Inside you will find practical ideas, useful explanations and simple activities designed to help you explore this subject.\n\nTake your time and enjoy reading.'
  },1);
 }else{
  left.style.background='white';
  left.style.color='#382d29';
  left.innerHTML=makePage(
   book.pages[currentPage-1],
   currentPage
  );

  if(currentPage===11){
   right.style.background='white';
   right.style.color='#382d29';
   right.innerHTML=makePage({
    heading:'Thank You for Reading',
    text:'Thank you for spending time with this guide.\n\nContinue exploring, learning and applying the ideas that are useful to you.'
   },12);
  }else{
   right.style.background='white';
   right.style.color='#382d29';
   right.innerHTML=makePage(
    book.pages[currentPage],
    currentPage+1
   );
  }
 }

 document.getElementById('pageCounter').textContent=
 (currentPage+1)+' of '+TOTAL_PAGES;

 document.getElementById('bookName').textContent=book.title;
 document.getElementById('bookPageInfo').textContent=book.description;

 const dots=document.getElementById('bookDots');
 dots.innerHTML='';

 for(let i=0;i<TOTAL_PAGES;i++){
  const dot=document.createElement('span');
  dot.className='book-dot'+(i===currentPage?' active':'');
  dots.appendChild(dot);
 }
}

function nextPage(){
 if(currentPage<TOTAL_PAGES-1){
  currentPage++;
  renderBookViewer();
 }
}

function previousPage(){
 if(currentPage>0){
  currentPage--;
  renderBookViewer();
 }
}

/* FAQ */
function toggleFaq(element){
 element.parentElement.classList.toggle('active');
}

/* SAMPLE BOOK GENERATOR */
let chapters=[];
let currentChapter=0;
let generatedTitle='';

function escapeHTML(str){
 return String(str).replace(/[&<>"']/g,c=>({
  '&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'
 })[c]);
}

function generateBook(){
 const topic=document.getElementById('bookTopic').value.trim();
 const audience=document.getElementById('bookAudience').value.trim()||'General readers';

 if(topic.length<5){
  document.getElementById('genStatus').textContent='Please enter a book topic.';
  return;
 }

 document.getElementById('genStatus').textContent='Creating your sample book...';
 document.getElementById('previewStatus').textContent='Working...';

 setTimeout(()=>{
  generatedTitle=topic.charAt(0).toUpperCase()+topic.slice(1);

  chapters=[
   {title:'Introduction',text:`Welcome to ${generatedTitle}.\n\nThis book is designed for ${audience}. It introduces the subject in a clear and approachable way.`},
   {title:'Understanding the Basics',text:`Explore the foundations of ${generatedTitle}.\n\nLearn the central concepts, understand the terminology and build your knowledge step by step.`},
   {title:'Essential Principles',text:`Discover the important principles behind this subject.\n\nOrganize your learning into useful sections and support factual information with reliable research.`},
   {title:'Practical Applications',text:`Explore examples and practical ways to apply what you have learned.\n\nAdapt the recommendations to your audience and circumstances.`},
   {title:'Common Challenges',text:`Understand common questions and difficulties.\n\nLook for reliable resources and additional information where necessary.`},
   {title:'Conclusion',text:`Thank you for reading ${generatedTitle}.\n\nContinue learning and developing your understanding of this topic.`}
  ];

  currentChapter=0;
  renderGeneratedBook();

  document.getElementById('genStatus').textContent='✓ Sample book created.';
  document.getElementById('previewStatus').textContent='Preview ready';
 },900);
}

function renderGeneratedBook(){
 document.getElementById('bookResult').innerHTML=`
 <div class="result-cover">
  <div>YOUR BRAND EDITION</div>
  <h2>${escapeHTML(generatedTitle)}</h2>
  <div>✦ A PRACTICAL GUIDE ✦</div>
 </div>
 <div class="result-content">
  <h3>Table of contents</h3>
  <div class="chapter-nav" id="chapterNav"></div>
  <h3 id="chapterTitle"></h3>
  <textarea id="chapterEditor"></textarea>
  <div class="result-actions">
   <button class="btn-primary" onclick="saveChapter()">Save changes</button>
   <button class="btn-primary" onclick="downloadBook()">Download book</button>
  </div>
 </div>`;

 renderChapter();
}

function renderChapter(){
 const nav=document.getElementById('chapterNav');
 const editor=document.getElementById('chapterEditor');

 if(!nav||!editor)return;

 nav.innerHTML='';

 chapters.forEach((chapter,index)=>{
  const button=document.createElement('button');
  button.textContent=(index+1)+'. '+chapter.title;
  button.className=index===currentChapter?'selected':'';

  button.onclick=()=>{
   saveChapter();
   currentChapter=index;
   renderChapter();
  };

  nav.appendChild(button);
 });

 document.getElementById('chapterTitle').textContent=chapters[currentChapter].title;
 editor.value=chapters[currentChapter].text;
}

function saveChapter(){
 const editor=document.getElementById('chapterEditor');
 if(editor&&chapters[currentChapter]){
  chapters[currentChapter].text=editor.value;
 }
}

function downloadBook(){
 saveChapter();

 let html=`<!DOCTYPE html><html><head><meta charset="UTF-8">
 <title>${escapeHTML(generatedTitle)}</title>
 <style>body{max-width:750px;margin:50px auto;padding:20px;font-family:Georgia;line-height:1.9}h1{text-align:center}h2{margin-top:40px}p{white-space:pre-line}</style>
 </head><body><h1>${escapeHTML(generatedTitle)}</h1>`;

 chapters.forEach(chapter=>{
  html+=`<h2>${escapeHTML(chapter.title)}</h2><p>${escapeHTML(chapter.text)}</p>`;
 });

 html+='</body></html>';

 const blob=new Blob([html],{type:'text/html;charset=utf-8'});
 const url=URL.createObjectURL(blob);
 const link=document.createElement('a');

 link.href=url;
 link.download='yourbrand-ebook.html';
 link.click();

 URL.revokeObjectURL(url);
}

/* INITIALIZE */
renderBookViewer();

</script>
</body>
</html>
