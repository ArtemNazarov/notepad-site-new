<script>
  import anime from "animejs/lib/anime.es.js";
  import { onMount } from "svelte";

  onMount(() => {
    const textWrapper = document.getElementById("product-slogan");
    textWrapper.innerHTML = textWrapper.textContent.replace(
      /\S/g,
      "<span class='letter'>$&</span>"
    );

    anime
      .timeline({ loop: false })
      .add({
        targets: "#product-slogan .letter",
        opacity: [0, 1],
        easing: "easeInOutQuad",
        duration: 2250,
        delay: (el, i) => 150 * (i + 1),
      })
      .add({
        targets: "#product-slogan h1",
        opacity: 0,
        duration: 1000,
        easing: "easeOutExpo",
        delay: 1000,
      });
  });
</script>

<div>
  <section id="main-banner" class="section">
    <div id="main-grid">
      <div>
        <div id="product-slogan">
          <h1>Keep your thoughts in a safe place</h1>
        </div>
        <button id="lift-button">
          <a href="/#products-download">START NOW </a>
        </button>
      </div>
      <div class="product-image">
        <img src="/assets/screenshots/1.png" alt="Banner" />
      </div>
    </div>
  </section>

  <section class="section section-grid">
    <div class="product-info">
      <h1>Fully customizable 🎨</h1>
      <span>You choose your own style settings and color themes</span>
    </div>
    <div class="product-screenshots">
      <div class="product-image">
        <img src="/assets/screenshots/2.png" alt="Color palette" />
      </div>
      <div class="product-image">
        <img src="/assets/screenshots/3.png" alt="Appearance settings" />
      </div>
    </div>
  </section>
  <section class="section section-grid">
    <div class="product-info even">
      <h1>Reliable</h1>
      <span
        >Your data are in safety with our out-of-the-box every day backup and
        Google Disk Sync 🔄</span
      >
    </div>
    <div class="product-screenshots">
      <div class="product-image">
        <img src="/assets/screenshots/5.png" alt="Backup info" />
      </div>
      <div class="product-image">
        <img src="/assets/screenshots/6.png" alt="Backups list" />
      </div>
    </div>
  </section>
  <section class="section section-grid">
    <div class="product-info">
      <h1>Multifunctional</h1>
      <span>Markdown edit and preview</span>
    </div>
    <div class="product-screenshots">
      <div class="product-image">
        <img src="/assets/screenshots/7.png" alt="Markdown edit" />
      </div>
      <div class="product-image">
        <img src="/assets/screenshots/8.png" alt="Markdown result" />
      </div>
    </div>
  </section>
  <!--"https://play.google.com/intl/en_us/badges/static/images/badges/en_badge_web_generic.png"-->
  <section id="products-download" class="section">
    <div class="product-link">
      <h1>Lite</h1>
      <div><img src="/assets/lite-qr.svg" alt="Lite version QR-code"></div>
      <div class="product-button">
        <a
          href="https://play.google.com/store/apps/details?id=ru.diman169.notepad.lite"
          ><img
            alt="Get it on Google Play"
            src="/assets/en_badge_web_generic.png"
          /></a
        >
      </div>
    </div>
    <div class="product-link">
      <h1>Pure</h1>
      <div><img src="/assets/pure-qr.svg" alt="Pure version QR-code"></div>
      <div class="product-button">
        <a
          href="https://play.google.com/store/apps/details?id=ru.diman169.notepad"
        >
          <img
            alt="Get it on Google Play"
            src="/assets/en_badge_web_generic.png"
          />
        </a>
      </div>
    </div>
    <div class="product-link">
      <h1>Secure</h1>
      <div><img src="/assets/pure-qr.svg" alt="Pure version QR-code"></div>
      <div class="product-button">
        <a
          href="https://play.google.com/store/apps/details?id=ru.diman169.notepad"
        >
          <img
            alt="Get it on Google Play"
            src="/assets/en_badge_web_generic.png"
          />
        </a>
      </div>
    </div>
  </section>
</div>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@100&display=swap");

  #main-banner {
    background-image: url("/assets/banner.jpg");
    width: 100%;
    background-repeat: no-repeat;
  }

  #main-grid {
    display: grid;
    grid-template-columns: 1fr;
    align-items: center;
    justify-items: center;
    text-align: center;
  }

  .section-grid {
    display: grid;
    grid-template-columns: 1fr;
  }

  .product-info {
    display: flex;
    justify-content: center;
    align-items: flex-start;
    flex-direction: column;
    font-size: 1.25rem;
    margin-bottom: 3rem;
  }

  .product-info h1 {
    margin-top: 0;
  }

  .product-screenshots {
    display: block;
    text-align: center;
  }

  .product-image img {
    width: 100%;
    height: 100%;
  }

  .product-screenshots img {
    margin-bottom: 3rem;
  }

  #products-download {
    display: grid;
    grid-template-columns: 1fr;
    background-image: url("/assets/products.png");
    color: #fff;
  }

  #products-download h1 {
    font-size: 3rem;
    font-family: 'Montserrat Light', sans-serif;
  }

  .product-link {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .product-button {
    height: 36vw;
  }

  .product-button img {
    width: 100%;
    height: 100%;
  }

  #product-slogan :global(.letter) {
    font-family: "Montserrat", sans-serif;
    font-weight: 700;
    font-size: 3rem;
    color: #fff;
  }

  #product-slogan {
    margin-bottom: 3rem;
  }

  #lift-button {
    /* border: none; */
    border-radius: 4px;
    padding: 20px 90px;
    color: #0E1821;
    background-image: linear-gradient(#14E3FF, #1FAFDD);
  }

  #lift-button a {
    text-decoration: none;
    color: #0E1821;
  }

  /* .panel {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100px;
    margin: 10px;
    -webkit-box-shadow: 10px 10px 20px 0px rgba(0, 0, 0, 0.5);
    box-shadow: 10px 10px 20px 0px rgba(0, 0, 0, 0.5);
  } */

  @media (min-width: 400px) {
    .product-info {
      font-size: 1.4rem;
    }
  }

  @media (min-width: 640px) {
    .product-screenshots {
      display: flex;
      justify-content: space-around;
    }
  }

  @media (min-width: 1024px) {
    #product-slogan :global(.letter) {
      color: #fff;
    }

    .section-grid {
      grid-template-columns: 1fr 1fr;
    }

    #main-grid {
      grid-template-columns: 1fr 1fr;
    }

    #products-download {
      grid-template-columns: 1fr 1fr 1fr;
    }

    .product-info {
      font-size: 1.5rem;
    }

    .product-info.even {
      order: 1;
      padding-left: 4rem;
    }

    .product-screenshots img {
      margin-bottom: 0;
    }

    .product-button {
      width: 430px;
      height: 170px;
    }

    .product-image {
      width: 306px;
      height: 648px;
    }
  }
</style>
