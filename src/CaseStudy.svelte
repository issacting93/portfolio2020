<script>
  import { fade } from "svelte/transition";
  let visible = true;
  let active01 = false;
  let active02 = false;
  let active03 = false;

  function typewriter(node, { speed = 5 }) {
    const valid =
      node.childNodes.length === 1 &&
      node.childNodes[0].nodeType === Node.TEXT_NODE;

    if (!valid) {
      throw new Error(
        `This transition only works on elements with a single text node child`
      );
    }

    const text = node.textContent;
    const duration = text.length / (speed * 0.01);

    return {
      duration,
      tick: (t) => {
        const i = ~~(text.length * t);
        node.textContent = text.slice(0, i);
      },
    };
  }

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
  const cases = [
    {
      no: "1",
      id: "ember",
      name: "Ember Design Language System",
      image: "/images/STEALTH.png",
    },
    {
      no: "2",
      id: "stepup",
      name: "StepUp",
      image: "https://proj-ash.vercel.app/images/DARK FUTURE.png",
    },
    {
      no: "3",
      id: "lynn",
      name: "lynn",
      image: "https://proj-ash.vercel.app/images/LYNN.png",
    },
  ];

  let password = "portfolioReview";
  let passwordInput = "";
  let showCase = false;
  let selectedCaseStudy = 0;
  const checkPassword = () => {
    if (passwordInput == password) {
      showCase = true;
      console.log("password is correct");
    } else {
      console.log("password is" + passwordInput);
    }
  };
  const onKeyPress = (e) => {
    if (e.charCode === 13) checkPassword();
  };
</script>

<section class="case-section">
  <div class="password-container">
    <div class="title">Case Studies</div>
    {#if showCase}{:else}
      <p>Please enter password to view case studies</p>

      <input
        class="password-input"
        bind:value={passwordInput}
        on:keypress={onKeyPress}
        placeholder="enter password"
      />
    {/if}
  </div>
  {#if active01}
    <div class="light-box" on:click={() => (active01 = !active01)}>
      <div class="pulseLoader" />
      <iframe
        style="border: 1px solid rgba(0, 0, 0, 0.1);"
        width="100%"
        height="100%"
        src="https://www.figma.com/embed?embed_host=share&url=https%3A%2F%2Fwww.figma.com%2Fproto%2FGEmhtqmH0KbyOf2Si9efgw%2FPortfolio-2022%3Fpage-id%3D101%253A2099%26node-id%3D102%253A3104%26viewport%3D241%252C48%252C0.08%26scaling%3Dscale-down-width%26starting-point-node-id%3D102%253A3104"
        allowfullscreen
      />
    </div>
  {/if}
  {#if active02}
    <div class="light-box" on:click={() => (active02 = !active02)}>
      <iframe
        style="border: 1px solid rgba(0, 0, 0, 0.1);"
        width="100%"
        height="100%"
        src="https://www.figma.com/embed?embed_host=share&url=https%3A%2F%2Fwww.figma.com%2Fproto%2FGEmhtqmH0KbyOf2Si9efgw%2FPortfolio-2022%3Fpage-id%3D101%253A2099%26node-id%3D109%253A2654%26viewport%3D344%252C48%252C0.16%26scaling%3Dmin-zoom%26starting-point-node-id%3D109%253A2654"
        allowfullscreen
      />
      <div class="pulseLoader" />
    </div>
  {/if}
  {#if active03}
    <div class="light-box" on:click={() => (active03 = !active03)}>
      <iframe
        style="border: 1px solid rgba(0, 0, 0, 0.1);"
        width="100%"
        height="100%"
        src="https://www.figma.com/embed?embed_host=share&url=https%3A%2F%2Fwww.figma.com%2Fproto%2FGEmhtqmH0KbyOf2Si9efgw%2FPortfolio-2022%3Fpage-id%3D101%253A2099%26node-id%3D351%253A2592%26viewport%3D344%252C48%252C0.38%26scaling%3Dmin-zoom%26starting-point-node-id%3D351%253A2592"
        allowfullscreen
      />
      <div class="pulseLoader" />
    </div>
  {/if}

  <div class="case-study-section" id="three">
    <div class="case-container">
      <div class="case-image">
        <img class="screen-img" src="images/thumbnail.png" alt="" />
      </div>
      <div class="case-text">
        <div class="case-title">CC4</div>

        <div class="case-description">
          As one of the 2 designers responsible for the Career Coach Platform,
          it is important to me to push the quality of design, research and
          operation in the product.
          <br />Here's how we have tackled it over the last 180 days.
        </div>
        {#if showCase}
          <button on:click={() => (active03 = !active03)}> Learn More </button>
        {:else}
          <img class="lock" src="images/lock.svg" alt="" />
        {/if}
      </div>
    </div>
  </div>
  <div class="case-study-section" id="three">
    <div class="case-container">
      <div class="case-image">
        <img class="screen-img" src="images/Screen.png" alt="" />
      </div>
      <div class="case-text">
        <div class="case-title">Ember Design Language System</div>

        <div class="case-description">
          Creating Singtel's Design Language System used across Digital
          Experience team. Here is how we have build a living, breathing system
          to cater to the needs of a growing design team over the course of 18
          months.
        </div>
        {#if showCase}
          <button on:click={() => (active01 = !active01)}>
            Read Case Study
          </button>
        {:else}
          <img class="lock" src="images/lock.svg" alt="" />
        {/if}
      </div>
    </div>
  </div>
  <div class="case-study-section" id="three">
    <div class="case-container">
      <div class="case-image">
        <img class="phone-img" src="images/phone-01.png" alt="" />
      </div>
      <div class="case-text">
        <div class="case-title">hi!Carnival</div>
        <div class="case-description">
          Singtel's first award winning gamification project which helped to
          drive MAU by 20% on our prepaid App.
        </div>
        {#if showCase}
          <button on:click={() => (active02 = !active02)}>
            Read Case Study
          </button>
        {:else}
          <img class="lock" src="images/lock.svg" alt="" />
        {/if}
      </div>
    </div>
  </div>
</section>

<style>
  button a {
    color: black;
  }

  .lock {
    margin-top: 24px;
  }
  section {
    padding: 80px;
    padding-top: 0px;
    background-color: rgb(26, 26, 26);
    height: auto;
  }
  button {
    padding: 8px 16px;
    margin: 16px 0px;
    font-family: "Barlow";
    transition: 0.2s all;
    border-radius: 50px;
  }

  button:hover {
    background-color: rgba(22, 22, 22, 0.9);
    color: white;
  }

  @keyframes slide-up {
    0% {
      height: 0px;
    }
    100% {
      height: auto;
    }
  }
  .case-study-section {
    font-weight: 100;
    font-size: 16px;
    line-height: 24px;
    text-align: center;
    padding: 40px;
    margin: auto;
    height: auto;
    width: 100%;

    animation-name: slide-up;
    animation-duration: 1.3s;
    animation-fill-mode: forwards;
  }

  .case-title {
    position: static;
    width: 455px;
    padding-bottom: 16px;
    font-family: Playfair Display;
    font-style: normal;
    font-weight: bold;
    font-size: 48px;
    line-height: 50px;
    color: white;
  }

  .screen-img {
    width: 100%;
    box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
    transition: 0.3s all;
  }

  .phone-img {
    height: 100%;
    box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
    transition: 0.3s all;
  }
  .screen-img:hover {
    transform: translateY(-2px);
    box-shadow: rgba(50, 50, 93, 0.25) 0px 50px 100px -20px,
      rgba(0, 0, 0, 0.3) 0px 30px 60px -30px;
  }
  .password-input {
    padding: 8px;
    background: #ff000005;
    color: white;
    border: 1px solid #ff00003d;
  }
  .password-input:focus {
    border: 2px solid red;
  }
  .phone-img:hover {
    transform: translateY(-2px);
    box-shadow: rgba(50, 50, 93, 0.25) 0px 50px 100px -20px,
      rgba(0, 0, 0, 0.3) 0px 30px 60px -30px;
  }
  .case-image {
    height: 100%;
    width: 50%;
    padding: 80px;
    text-align: center;
  }
  .case-text {
    height: 100%;
    width: 50%;
    max-width: 500px;
    padding-right: 80px;
    font-weight: 400;
  }
  .case-container {
    display: flex;
    max-width: 1200px;
    height: 100%;
    margin: auto;
    text-align: left;
    align-items: center;
    color: white;
  }
  p {
    color: white;
  }
  .light-box {
    position: fixed;
    height: 100vh;
    width: 100%;
    background-color: rgba(1, 1, 1, 0.95);
    z-index: 100;
    top: 0px;
    margin: auto;
    padding: 40px;
    left: 0px;
    right: 0px;
  }
  .active {
    display: none;
  }
  .title {
    position: relative;
    top: 0px;
  }
  iframe {
    border-radius: 24px;
    z-index: 10;
    position: relative;
  }
  .case-image img {
    border-radius: 16px;
  }

  .pulseLoader {
    width: 4em;
    height: 4em;
    border-radius: 4em;
    background-color: #1a1a1a;
    outline: 1px solid transparent;
    animation: pulseanim 1.2s ease-in-out infinite;
    position: fixed;
    top: 0px;
    left: 0px;
    right: 0px;
    bottom: 0px;
    margin: auto;
    z-index: 1;
  }
  .password-container {
    text-align: center;
    margin: 40px;
  }
  @keyframes pulseanim {
    0% {
      transform: scale(0);
      opacity: 0.8;
    }
    100% {
      transform: scale(1);
      opacity: 0;
    }
  }
  @media only screen and (max-width: 800px) {
    section {
      padding: 0px;
    }

    iframe {
      border-radius: 0px;
    }
    .case-container {
      display: flex;
      max-width: 1200px;
      height: 100%;
      margin: auto;
      text-align: center;
      align-items: center;
      flex-direction: column;
    }
    .light-box {
      padding: 10px;
      padding-top: 20px;
      border-radius: 0px;
    }
    .case-text {
      width: 100%;
      padding: 40px;
      max-width: 100%;
    }
    .case-title {
      margin: auto;
      height: auto;
      max-width: calc(100vw - 80px);
      width: 100%;
    }
    .case-description {
      max-width: 600px;
      margin: auto;
      padding-top: 20px;
      max-width: calc(100vw - 80px);
      color: white;
    }
    .case-image {
      width: 100%;
      padding: 40px;
    }
    .screen-img {
      max-width: calc(100vw - 80px);
    }
  }
</style>
