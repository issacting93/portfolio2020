<script>
  import Arrow from "./arrow.svelte";
  import MouseTracking from "./ParallaxComponent.svelte";
  import Blob from "./Blob.svelte";
  import SVGPlay from "./SVGPlay.svelte";

  let active = false;
  window.addEventListener("load", function () {
    // Get the container element
    var spinebtnContainer = document.getElementById("spine-controller");

    // Get all buttons with class="btn" inside the container
    var btnSpine = spinebtnContainer.getElementsByClassName("spine-unit");

    // Loop through the buttons and add the active class to the current/clicked button
    for (var i = 0; i < btnSpine.length; i++) {
      btnSpine[i].addEventListener("mouseover", function () {
        var current = document.getElementsByClassName(" active");
        current[0].className = current[0].className.replace(" active", "");
        this.className += " active";
      });
    }
  });
</script>

<section class="hero-section" id="one">
  <div class="hero-text">
    My name is Issac.
    <br /> If you'll indulge me, <br />
    I'd like to design the future
  </div>

  <div class="bottom">
    <div class="banner-btn-container">
      Show case studies

      <a href="#case-studies">
        <div class="arrow"><Arrow /></div>
      </a>
    </div>

    <div class="video-click">
      <a on:click={() => (active = !active)}>
        <SVGPlay />
      </a>
    </div>
  </div>
  <div class="hero-interactive">
    <!--
   <h2 class="hero-text hero-text-01 top"><span> MY NAME IS ISSAC </span></h2>
    <h2 class="hero-text   hero-text-02">
      <span> if you’ll indulge me </span>
    </h2>
    <h2 class="hero-text  hero-text-03  ">
      <span> I’d Like to design the Future </span>
    </h2>

      -->

    {#if active}
      <div class="light-box" on:click={() => (active = !active)}>
        <div class="pulseLoader" />
        <div style="height:100% ;position:relative;">
          <div style="padding:54.72% 0 0 0;position:relative;">
            <iframe
              class="video-frame"
              src="https://player.vimeo.com/video/668675980?h=9e015db434&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479"
              frameborder="0"
              allow="autoplay; fullscreen; picture-in-picture"
              allowfullscreen
              style="position:absolute;top:0;left:0;width:100%;height:100%;"
              title="Zac Ting Showreel"
            />
          </div>
          <script src="https://player.vimeo.com/api/player.js"></script>
        </div>
        <script src="https://player.vimeo.com/api/player.js"></script>

        <a class="close-btn" on:click={() => (active = !active)}> ⤫ </a>
      </div>
    {/if}
  </div>
  <MouseTracking />
</section>

<style>
  .bottom {
    position: absolute;
    bottom: 80px;
    display: flex;
    justify-content: center;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 9;
  }

  .banner-btn-container {
    text-align: center;
    color: white;
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 0px 20px;
  }
  .flash-warning {
    font-size: 14px;
  }
  .close-btn {
    z-index: 140;
    position: absolute;
    left: 0px;
    right: 0px;
    margin: auto;
    height: auto;
    width: auto;
    border-radius: 100%;
    text-align: center;
    padding: 4px;
    bottom: 20px;
    font-size: 34px;
  }
  .video-frame {
    max-height: 90vh;
  }
  .close-btn {
    font-weight: 500;
  }
  .close-btn:hover {
    transform: scale(1.5);
  }
  .video-click {
    color: white;
    margin: auto;
    text-align: center;
    position: absolute;
    vertical-align: middle;
    bottom: 40px;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 5;
    transition: all 0.2s;
    font-size: 32px;
    filter: saturate(0.1);
    transition: all 0.2s;
    margin-bottom: 40px;
  }
  .video-click:hover {
    filter: saturate(1);
  }

  .video-click:active {
    filter: blur(3px);
  }
  .hero-text {
    color: white;
  }
  .hero-interactive {
    margin-top: 30px;
    width: 100%;
  }
  .hero-text {
    font-family: "Barlow";
    height: fit-content;
    vertical-align: middle;
    justify-content: center;
    align-content: center;
    flex-direction: column;
    display: flex;
    align-items: center;
    text-align: center;
    z-index: 2;
    position: absolute;
    left: 0px;
    right: 0px;
    padding: 20px;
    transform: translate(0, -50%);
    letter-spacing: 0.1em;
    font-weight: 100;
    opacity: 0;
    animation: fadein 0.4s ease-out forwards;
    animation-delay: 2s;
    font-size: 5vh;
    line-height: initial;
    width: 50%;
    margin: auto;
    letter-spacing: 0px;
    top: 30%;
  }

  .hero-text-01 {
    color: white;
    text-align: center;
    position: absolute;
    text-align: center;
    left: 0px;
    right: 0px;
    letter-spacing: 0.1em;
    z-index: 2;
    height: fit-content;
    vertical-align: middle;
    justify-content: center;
    align-content: center;
    flex-direction: column;
    font-family: "Barlow";
  }

  .arrow {
    width: 54px;
    height: 54px;
    cursor: pointer;
  }

  .hero-text-01.bottom {
    display: flex;
    flex-direction: column;
    width: fit-content;
    bottom: 10vh;
    align-items: center;
    margin: auto;
    font-weight: 100;
    opacity: 0;
    animation: fadein 4s ease-in forwards;
    animation-delay: 4s;
  }

  .hero-text-01 span,
  .hero-text-02 span,
  .hero-text-03 span {
    width: 100%;
    float: left;
    font-family: "Barlow";
    font-size: 16px;
    font-weight: 100;
    color: #ffffff;
    -webkit-clip-path: polygon(100% 0, 100% 100%, 0 100%, 0 80%);
    clip-path: polygon(100% 0, 100% 100%, 0 100%, 0 80%);
    transform: translateY(-50px);
    opacity: 0;
    animation-name: titleAnimation;
    animation-timing-function: ease;
    animation-duration: 3s;
  }

  .hero-text-01 span {
    animation-delay: 0.6s;
    animation-fill-mode: forwards;
    -webkit-animation-fill-mode: forwards;
  }
  .hero-text-01 span:first-child {
    animation-delay: 0.7s;
  }
  .hero-text-01 span:last-child {
    animation-delay: 0.5s;
  }

  .hero-text-02 {
    font-weight: 100;
  }
  .hero-text-02 span {
    animation-delay: 3.1s;
    animation-fill-mode: forwards;
    -webkit-animation-fill-mode: forwards;
  }
  .hero-text-02 span:first-child {
    animation-delay: 3.2s;
  }
  .hero-text-02 span:last-child {
    animation-delay: 3.5s;
  }
  .light-box {
    height: 100vh;
    position: static;
    width: auto;
    background-color: rgba(1, 1, 1, 0.95);
    z-index: 100;
    top: 0px;
    margin: auto;
    padding: 20px;
    padding-top: 0px;
    left: 0px;
    right: 0px;
  }
  .active {
    display: none;
  }
  iframe {
    border-radius: 16px;
    z-index: 10;
    position: relative;
  }
  .hero-text-03 {
    position: absolute;
    font-weight: 600;
  }
  .hero-text-03 span {
    animation-delay: 6.1s;
    animation-fill-mode: forwards;
    -webkit-animation-fill-mode: forwards;
    font-weight: 600;
  }
  .hero-text-03 span:first-child {
    animation-delay: 6.2s;
  }
  .hero-text-03 span:last-child {
    animation-delay: 6s;
  }
  @media screen and (max-width: 800px) {
    .hero-text-01.bottom {
      margin-bottom: 30%;
      animation-delay: 1s;
    }
    .video-click {
      bottom: 40px;
    }
  }

  @keyframes titleAnimation {
    0% {
      transform: translateY(-50px);
      opacity: 0;
      -webkit-clip-path: polygon(100% 0, 100% 100%, 0 100%, 0 80%);
      clip-path: polygon(100% 0, 100% 100%, 0 100%, 0 80%);
    }
    20% {
      transform: translateY(0);
      opacity: 1;
      -webkit-clip-path: polygon(100% 0, 100% 100%, 0 100%, 0 15%);
      clip-path: polygon(100% 0, 100% 100%, 0 100%, 0 15%);
    }
    80% {
      transform: translateY(0);
      opacity: 1;
      -webkit-clip-path: polygon(100% 0, 100% 100%, 0 100%, 0 15%);
      clip-path: polygon(100% 0, 100% 100%, 0 100%, 0 15%);
    }
    100% {
      transform: translateY(50px);
      opacity: 0;
      -webkit-clip-path: polygon(100% 0, 100% 0%, 0 100%, 0 100%);
      clip-path: polygon(100% 0, 100% 0%, 0 100%, 0 100%);
    }
  }
</style>
