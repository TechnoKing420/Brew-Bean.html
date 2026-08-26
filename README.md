<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Brew & Bean Coffee House — specialty coffee, fresh pastries and good vibes.">
  <title>Brew & Bean Coffee House</title>

  <style>
    :root {
      --espresso: #2b1b14;
      --coffee: #5a3825;
      --caramel: #b97845;
      --cream: #f7f0e5;
      --light: #fffaf3;
      --sage: #77816a;
      --white: #ffffff;
      --text: #3b302a;
      --muted: #756b64;
      --shadow: 0 15px 40px rgba(43, 27, 20, 0.10);
      --radius: 22px;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: Arial, Helvetica, sans-serif;
      color: var(--text);
      background: var(--light);
      line-height: 1.6;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    img {
      max-width: 100%;
      display: block;
    }

    /* NAVIGATION */

    header {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      z-index: 1000;
      background: rgba(255, 250, 243, 0.94);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid rgba(43, 27, 20, 0.08);
    }

    nav {
      max-width: 1180px;
      margin: auto;
      height: 78px;
      padding: 0 24px;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .logo {
      font-family: Georgia, serif;
      font-size: 1.45rem;
      font-weight: bold;
      color: var(--espresso);
    }

    .logo span {
      color: var(--caramel);
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 30px;
      list-style: none;
    }

    .nav-links a {
      font-size: 0.92rem;
      font-weight: 600;
      transition: color 0.2s ease;
    }

    .nav-links a:hover {
      color: var(--caramel);
    }

    .nav-cta {
      background: var(--espresso);
      color: var(--white) !important;
      padding: 11px 19px;
      border-radius: 50px;
    }

    .nav-cta:hover {
      background: var(--caramel);
    }

    .menu-toggle {
      display: none;
      border: 0;
      background: none;
      font-size: 1.7rem;
      cursor: pointer;
    }

    /* HERO */

    .hero {
      min-height: 100vh;
      padding: 150px 24px 90px;
      background:
        linear-gradient(90deg, rgba(43, 27, 20, 0.92), rgba(43, 27, 20, 0.56)),
        url("https://images.unsplash.com/photo-1495474472287-4d71bcdd2085?auto=format&fit=crop&w=1800&q=85")
        center/cover;
      color: var(--white);
      display: flex;
      align-items: center;
    }

    .hero-content {
      max-width: 1180px;
      width: 100%;
      margin: auto;
    }

    .eyebrow {
      color: #e9b982;
      text-transform: uppercase;
      letter-spacing: 3px;
      font-size: 0.76rem;
      font-weight: bold;
      margin-bottom: 18px;
    }

    .hero h1 {
      max-width: 680px;
      font-family: Georgia, serif;
      font-size: clamp(3.2rem, 7vw, 6.2rem);
      line-height: 0.98;
      margin-bottom: 25px;
    }

    .hero p {
      max-width: 570px;
      color: #f2e9de;
      font-size: 1.1rem;
      margin-bottom: 34px;
    }

    .buttons {
      display: flex;
      flex-wrap: wrap;
      gap: 14px;
    }

    .btn {
      display: inline-block;
      padding: 14px 24px;
      border-radius: 50px;
      font-weight: bold;
      transition: 0.25s ease;
      cursor: pointer;
      border: none;
    }

    .btn-primary {
      background: #d69a61;
      color: var(--espresso);
    }

    .btn-primary:hover {
      background: var(--white);
      transform: translateY(-2px);
    }

    .btn-outline {
      color: var(--white);
      border: 1px solid rgba(255,255,255,.5);
    }

    .btn-outline:hover {
      background: var(--white);
      color: var(--espresso);
    }

    /* GENERAL */

    section {
      padding: 100px 24px;
    }

    .container {
      max-width: 1180px;
      margin: auto;
    }

    .section-heading {
      max-width: 680px;
      margin-bottom: 50px;
    }

    .section-heading.center {
      text-align: center;
      margin-left: auto;
      margin-right: auto;
    }

    .section-heading h2 {
      font-family: Georgia, serif;
      font-size: clamp(2.2rem, 5vw, 3.5rem);
      color: var(--espresso);
      line-height: 1.1;
      margin-bottom: 16px;
    }

    .section-heading p {
      color: var(--muted);
    }

    /* ABOUT */

    .about {
      background: var(--cream);
    }

    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 70px;
      align-items: center;
    }

    .about-image {
      height: 540px;
      border-radius: var(--radius);
      overflow: hidden;
      box-shadow: var(--shadow);
    }

    .about-image img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .about-copy h2 {
      font-family: Georgia, serif;
      color: var(--espresso);
      font-size: 3rem;
      line-height: 1.1;
      margin-bottom: 22px;
    }

    .about-copy p {
      color: var(--muted);
      margin-bottom: 20px;
    }

    .signature {
      margin-top: 30px;
      font-family: Georgia, serif;
      font-size: 1.3rem;
      color: var(--coffee);
    }

    /* MENU */

    .menu-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 22px;
    }

    .menu-card {
      background: var(--white);
      border: 1px solid #eee4d7;
      border-radius: var(--radius);
      padding: 30px;
      transition: 0.25s ease;
    }

    .menu-card:hover {
      transform: translateY(-7px);
      box-shadow: var(--shadow);
    }

    .menu-icon {
      font-size: 2rem;
      margin-bottom: 18px;
    }

    .menu-card h3 {
      font-family: Georgia, serif;
      font-size: 1.5rem;
      color: var(--espresso);
      margin-bottom: 9px;
    }

    .menu-card p {
      color: var(--muted);
      font-size: .93rem;
      margin-bottom: 20px;
    }

    .price {
      color: var(--caramel);
      font-weight: bold;
      font-size: 1.05rem;
    }

    /* SPECIAL */

    .special {
      background: var(--espresso);
      color: var(--white);
    }

    .special-grid {
      display: grid;
      grid-template-columns: 1.1fr .9fr;
      gap: 70px;
      align-items: center;
    }

    .special h2 {
      font-family: Georgia, serif;
      font-size: clamp(2.4rem, 5vw, 4rem);
      line-height: 1.05;
      margin-bottom: 20px;
    }

    .special p {
      color: #d8cbc0;
      max-width: 520px;
      margin-bottom: 28px;
    }

    .offer {
      background: #3a261d;
      border: 1px solid rgba(255,255,255,.12);
      border-radius: var(--radius);
      padding: 40px;
      text-align: center;
    }

    .offer small {
      color: #d69a61;
      text-transform: uppercase;
      letter-spacing: 2px;
      font-weight: bold;
    }

    .offer strong {
      display: block;
      font-family: Georgia, serif;
      font-size: 2.3rem;
      margin: 12px 0;
    }

    /* TESTIMONIALS */

    .testimonials {
      background: #fffaf3;
    }

    .reviews {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 22px;
    }

    .review {
      background: var(--white);
      border-radius: var(--radius);
      padding: 30px;
      box-shadow: 0 8px 30px rgba(43,27,20,.06);
    }

    .stars {
      color: #c8874e;
      margin-bottom: 15px;
      letter-spacing: 2px;
    }

    .review p {
      color: var(--muted);
      margin-bottom: 22px;
    }

    .review strong {
      color: var(--espresso);
    }

    /* VISIT */

    .visit {
      background: var(--cream);
    }

    .visit-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 30px;
    }

    .visit-card {
      background: var(--white);
      border-radius: var(--radius);
      padding: 40px;
    }

    .visit-card h3 {
      font-family: Georgia, serif;
      color: var(--espresso);
      font-size: 1.7rem;
      margin-bottom: 20px;
    }

    .hours {
      display: grid;
      gap: 10px;
    }

    .hours div {
      display: flex;
      justify-content: space-between;
      border-bottom: 1px solid #eee3d7;
      padding-bottom: 8px;
    }

    .contact-line {
      margin-bottom: 14px;
      color: var(--muted);
    }

    .contact-line strong {
      color: var(--espresso);
    }

    /* FOOTER */

    footer {
      background: #1d120e;
      color: #cfc2b8;
      padding: 50px 24px 30px;
    }

    .footer-grid {
      max-width: 1180px;
      margin: auto;
      display: grid;
      grid-template-columns: 1.5fr 1fr 1fr;
      gap: 50px;
      padding-bottom: 40px;
    }

    footer h3 {
      color: var(--white);
      font-family: Georgia, serif;
      margin-bottom: 15px;
      font-size: 1.3rem;
    }

    footer p,
    footer a {
      font-size: .9rem;
      color: #aa9c92;
    }

    footer a:hover {
      color: #d69a61;
    }

    .footer-bottom {
      max-width: 1180px;
      margin: auto;
      padding-top: 25px;
      border-top: 1px solid rgba(255,255,255,.1);
      font-size: .82rem;
      color: #887b72;
    }

    /* TOAST */

    .toast {
      position: fixed;
      right: 25px;
      bottom: 25px;
      background: var(--espresso);
      color: var(--white);
      padding: 15px 22px;
      border-radius: 12px;
      box-shadow: var(--shadow);
      transform: translateY(120px);
      transition: .3s ease;
      z-index: 2000;
    }

    .toast.show {
      transform: translateY(0);
    }

    /* RESPONSIVE */

    @media (max-width: 800px) {
      .menu-toggle {
        display: block;
      }

      .nav-links {
        position: absolute;
        top: 78px;
        left: 0;
        width: 100%;
        background: var(--light);
        flex-direction: column;
        align-items: stretch;
        gap: 0;
        padding: 10px 24px 25px;
        display: none;
      }

      .nav-links.open {
        display: flex;
      }

      .nav-links li a {
        display: block;
        padding: 13px 0;
      }

      .nav-cta {
        text-align: center;
      }

      .about-grid,
      .special-grid,
      .visit-grid {
        grid-template-columns: 1fr;
      }

      .menu-grid,
      .reviews {
        grid-template-columns: 1fr;
      }

      .about-image {
        height: 380px;
      }

      .footer-grid {
        grid-template-columns: 1fr;
        gap: 30px;
      }

      section {
        padding: 75px 20px;
      }
    }
  </style>
</head>

<body>

  <header>
    <nav>
      <a href="#home" class="logo">Brew <span>&</span> Bean</a>

      <button class="menu-toggle" aria-label="Open menu" onclick="toggleMenu()">
        ☰
      </button>

      <ul class="nav-links" id="navLinks">
        <li><a href="#about" onclick="closeMenu()">About</a></li>
        <li><a href="#menu" onclick="closeMenu()">Menu</a></li>
        <li><a href="#special" onclick="closeMenu()">Special</a></li>
        <li><a href="#visit" onclick="closeMenu()">Visit</a></li>
        <li><a href="#visit" class="nav-cta" onclick="closeMenu()">Order Now</a></li>
      </ul>
    </nav>
  </header>

  <main>

    <!-- HERO -->
    <section class="hero" id="home">
      <div class="hero-content">
        <div class="eyebrow">Specialty Coffee • Freshly Made</div>

        <h1>Your morning, brewed better.</h1>

        <p>
          Beautiful coffee, freshly baked treats and a welcoming space
          designed for slow mornings, good conversations and great ideas.
        </p>

        <div class="buttons">
          <a href="#menu" class="btn btn-primary">Explore Our Menu</a>
          <a href="#visit" class="btn btn-outline">Find Us</a>
        </div>
      </div>
    </section>

    <!-- ABOUT -->
    <section class="about" id="about">
      <div class="container about-grid">

        <div class="about-image">
          <img
            src="https://images.unsplash.com/photo-1501339847302-ac426a4a7cbb?auto=format&fit=crop&w=1000&q=85"
            alt="Coffee shop interior">
        </div>

        <div class="about-copy">
          <div class="eyebrow">Our Story</div>

          <h2>A little coffee shop with a big heart.</h2>

          <p>
            Brew & Bean Coffee House was created around one simple idea:
            great coffee should bring people together.
          </p>

          <p>
            From carefully prepared espresso to freshly baked pastries,
            everything we serve is made with quality and care.
          </p>

          <div class="signature">Made with care, one cup at a time.</div>
        </div>

      </div>
    </section>

    <!-- MENU -->
    <section id="menu">
      <div class="container">

        <div class="section-heading center">
          <div class="eyebrow">The Menu</div>
          <h2>Good coffee. Good food. Good mood.</h2>
          <p>
            A few of our customer favourites, made fresh throughout the day.
          </p>
        </div>

        <div class="menu-grid">

          <article class="menu-card">
            <div class="menu-icon">☕</div>
            <h3>Signature Latte</h3>
            <p>
              Smooth espresso, silky steamed milk and a touch of caramel.
            </p>
            <div class="price">R42</div>
          </article>

          <article class="menu-card">
            <div class="menu-icon">🍫</div>
            <h3>Mocha</h3>
            <p>
              Rich chocolate combined with espresso and velvety milk.
            </p>
            <div class="price">R45</div>
          </article>

          <article class="menu-card">
            <div class="menu-icon">🥐</div>
            <h3>Butter Croissant</h3>
            <p>
              Golden, flaky and freshly baked. Perfect with your morning brew.
            </p>
            <div class="price">R28</div>
          </article>

          <article class="menu-card">
            <div class="menu-icon">🧊</div>
            <h3>Iced Coffee</h3>
            <p>
              Chilled espresso, creamy milk and plenty of ice.
            </p>
            <div class="price">R40</div>
          </article>

          <article class="menu-card">
            <div class="menu-icon">🍰</div>
            <h3>Carrot Cake</h3>
            <p>
              Moist spiced carrot cake finished with creamy frosting.
            </p>
            <div class="price">R38</div>
          </article>

          <article class="menu-card">
            <div class="menu-icon">🥪</div>
            <h3>Breakfast Toastie</h3>
            <p>
              Toasted sourdough with egg, cheese and your choice of filling.
            </p>
            <div class="price">R55</div>
          </article>

        </div>
      </div>
    </section>

    <!-- SPECIAL -->
    <section class="special" id="special">
      <div class="container special-grid">

        <div>
          <div class="eyebrow">This Week</div>

          <h2>Make your morning a little sweeter.</h2>

          <p>
            Start your day with one of our signature coffees and something
            freshly baked from the counter.
          </p>

          <a href="#visit" class="btn btn-primary">Visit Brew & Bean</a>
        </div>

        <div class="offer">
          <small>Morning Special</small>
          <strong>2 Coffees + 1 Pastry</strong>
          <p>Perfect for sharing. Available while stocks last.</p>
        </div>

      </div>
    </section>

    <!-- REVIEWS -->
    <section class="testimonials">
      <div class="container">

        <div class="section-heading center">
          <div class="eyebrow">Kind Words</div>
          <h2>What our customers say</h2>
        </div>

        <div class="reviews">

          <article class="review">
            <div class="stars">★★★★★</div>
            <p>
              “Beautiful coffee, friendly service and the perfect atmosphere
              to start my day.”
            </p>
            <strong>— Sarah M.</strong>
          </article>

          <article class="review">
            <div class="stars">★★★★★</div>
            <p>
              “The signature latte is incredible. I came in for one coffee
              and ended up staying for two.”
            </p>
            <strong>— Daniel K.</strong>
          </article>

          <article class="review">
            <div class="stars">★★★★★</div>
            <p>
              “Such a warm little space. Great food, great coffee and lovely
              attention to detail.”
            </p>
            <strong>— Mia R.</strong>
          </article>

        </div>
      </div>
    </section>

    <!-- VISIT -->
    <section class="visit" id="visit">
      <div class="container">

        <div class="section-heading">
          <div class="eyebrow">Come Say Hi</div>
          <h2>Your table is waiting.</h2>
          <p>
            Drop in for your morning coffee, catch up with friends or settle
            in with your laptop and stay awhile.
          </p>
        </div>

        <div class="visit-grid">

          <div class="visit-card">
            <h3>Opening Hours</h3>

            <div class="hours">
              <div>
                <span>Monday – Friday</span>
                <strong>07:00 – 17:00</strong>
              </div>

              <div>
                <span>Saturday</span>
                <strong>08:00 – 16:00</strong>
              </div>

              <div>
                <span>Sunday</span>
                <strong>08:00 – 14:00</strong>
              </div>
            </div>
          </div>

          <div class="visit-card">
            <h3>Get In Touch</h3>

            <p class="contact-line">
              <strong>Location:</strong> 24 Bean Street
            </p>

            <p class="contact-line">
              <strong>Phone:</strong> 000 000 0000
            </p>

            <p class="contact-line">
              <strong>Email:</strong> hello@brewandbean.example
            </p>

            <button class="btn btn-primary" onclick="showMessage()">
              Order / Enquire
            </button>
          </div>

        </div>
      </div>
    </section>

  </main>

  <!-- FOOTER -->

  <footer>
    <div class="footer-grid">

      <div>
        <h3>Brew & Bean</h3>
        <p>
          Specialty coffee, fresh pastries and good vibes.
        </p>
      </div>

      <div>
        <h3>Explore</h3>
        <p><a href="#about">Our Story</a></p>
        <p><a href="#menu">Menu</a></p>
        <p><a href="#special">Specials</a></p>
      </div>

      <div>
        <h3>Social</h3>
        <p><a href="#">Instagram</a></p>
        <p><a href="#">TikTok</a></p>
        <p><a href="#">Facebook</a></p>
      </div>

    </div>

    <div class="footer-bottom">
      © 2026 Brew & Bean Coffee House. Fictional demo website created for portfolio purposes.
    </div>
  </footer>

  <div class="toast" id="toast">
    Thanks! This is a demo enquiry button.
  </div>

  <script>
    function toggleMenu() {
      document.getElementById("navLinks").classList.toggle("open");
    }

    function closeMenu() {
      document.getElementById("navLinks").classList.remove("open");
    }

    function showMessage() {
      const toast = document.getElementById("toast");

      toast.classList.add("show");

      setTimeout(() => {
        toast.classList.remove("show");
      }, 3000);
    }
  </script>

</body>
</html>
