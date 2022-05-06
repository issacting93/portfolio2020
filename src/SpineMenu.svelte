<script>
  import SpineUnitLeft from "./SVGSpineUnitLeft.svelte";
  import SpineUnitRight from "./SVGSpineUnitRight.svelte";
  import ScifiFrame from "./SVGscifiFrame.svelte";

  let visible = false;

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
  const projects = [
    {
      no: "1",
      id: "stealth",
      name: "HOME",
      image: " /images/STEALTH.png",
      link: "https://www.behance.net/gallery/112545991/Pyke-Stealth-game",
    },
    {
      no: "2",
      id: "CASE STUDIES",
      name: "Dark Future",
      image: "images/DARK FUTURE.png",
      link: "https://www.behance.net/gallery/71387117/Dark-Future",
    },
    {
      no: "3",
      id: "lynn",
      name: "ABOUT",
      image: "images/LYNN.png",
      link: "https://zacting.itch.io/lynn",
    },
    {
      no: "4",
      id: "icarus",
      name: "PERSONAL WORKS",
      image: "/images/ICARUS.png",
      link: "https://www.behance.net/gallery/99721631/STEAMPUNK-HUD-DESIGNS",
    },
    {
      no: "5",
      id: "findMe",
      name: "FIND ME",
      image: "images/THE DIVISION.png",
      link: "https://www.behance.net/gallery/108280961/DIVISION-III-Fan-art",
    },
  ];

  let selectedProject = 0;
</script>

<section class="section-03" id="personal-works">
  <div class="spine-container" id="spine-controller">
    <div class="spine">
      <ul class="spine-left">
        <li>
          <SpineUnitLeft />
        </li>
        <li><SpineUnitLeft /></li>
        <li>
          <SpineUnitLeft />
        </li>
        <li>
          <SpineUnitLeft />
        </li>
        <li>
          <SpineUnitLeft />
        </li>
      </ul>
      <ul class="spine-right">
        <li>
          <SpineUnitRight />
        </li>
        <li>
          <SpineUnitRight />
        </li>
        <li>
          <SpineUnitRight />
        </li>
        <li>
          <SpineUnitRight />
        </li>
        <li>
          <SpineUnitRight />
        </li>
      </ul>
      <ul class="spine-controller-ul dot-nav">
        <li class="  dot">
          <a href="#one" class="glow">
            <span><div class="menu-label glow">Home</div> </span>
          </a>
          <div />
        </li>
        <li class="  dot">
          <a href="#case-studies" class="glow">
            <span><div class="menu-label  glow">Case Studies</div> </span>
          </a>
        </li>
        <li class=" dot">
          <a href="#personal-works" class="glow">
            <span><div class="menu-label  glow">Personal Works</div> </span>
          </a>
        </li>
        <li class="  dot">
          <a href="#about" class="glow">
            <span><div class="menu-label  glow">About</div> </span>
          </a>
        </li>
        <li class="  dot">
          <a href="#find-me" class="glow">
            <span><div class="menu-label  glow">Find Me</div> </span>
          </a>
        </li>
      </ul>
    </div>
  </div>
</section>

<style>
  section {
    height: 100vh;
  }
  .menu-label {
    color: rgb(235, 87, 87);
  }
  .glow {
    text-align: center;
    transition: all 0.2s;
  }
  .glow span {
    color: #eb5757;
    text-shadow: 0 0 2px #eb5757, 0 0 10px #ffffff, 0 0 20px #eb5757,
      0 0 30px #eb5757, 0 0 40px #eb5757, 0 0 50px #eb5757;
    -webkit-animation: blink 3.5s infinite alternate;
    animation: blink 3.5s infinite alternate;
  }
  .glow:hover span {
    font-weight: 500;
  }

  @-webkit-keyframes blink {
    100% {
      text-shadow: 0 0 2px #eb5757, 0 0 10px #eb3700, 0 0 20px #eb5757,
        0 0 40px #eb5757, 0 0 70px #eb5757, 0 0 80px #eb5757;
    }
  }

  @keyframes blink {
    100% {
      text-shadow: 0 0 2px #eb3700, 0 0 10px #eb3700, 0 0 20px #eb3700,
        0 0 40px #eb3700, 0 0 70px #eb3700, 0 0 80px #eb3700;
    }
  }
  @keyframes open-spine {
    0% {
      margin-top: -80px;
      opacity: 0;
      -webkit-transform: rotate3d(0, 1, 0, 180deg);
    }
    30% {
      opacity: 1;
      -webkit-transform: rotate3d(0, 1, 0, 270deg);
    }
    100% {
      margin-top: 0px;
      opacity: 1;
      -webkit-transform: rotate3d(0, 1, 0, 360deg);
    }
  }

  .spine-container .spine-controller-ul {
    bottom: 0px;
  }
  .spine-controller-ul {
    left: 0px;
    top: -40px;
    right: 0px;
    position: absolute;
    display: flex;
    align-content: center;
    justify-content: space-around;
    width: fit-content;
    align-items: center;
    margin: auto;
    height: fit-content;
    flex-direction: column;
    transform: translate(0px, 0px);
    transition: all 0.3s ease-out;
  }
  .menu-label.glow:hover {
    border: 1px solid rgb(235, 87, 87);
    padding: 4px 16px;
    border-radius: 16px;
  }
  li.dot {
    margin-top: 0px;
    opacity: 0;
  }
  section {
    margin-top: 0px;
    width: 100%;
  }
  .spine-container {
    top: 0px;
  }
  .spine-container li.dot {
    margin-top: 80px;
    opacity: 1;
  }
  .spine-container .spine-left li,
  .spine-container .spine-right li {
    margin-top: 0px;
    opacity: 1;
    animation-name: open-spine;
    animation-duration: 0.7s;
    animation-fill-mode: forwards;
  }

  .spine-container .spine-controller-ul {
    top: 60px;
  }
  .title {
    top: 0px;
  }
  .frame-container {
    height: 100%;
    position: absolute;
    left: 0px;
    right: 0px;
    top: 95px;
    bottom: 0px;
    opacity: 0.6;
  }
  .spine-unit {
    transition: all 1s;
  }
  .frame-container:hover {
    opacity: 0.1;
  }
  .text {
    z-index: 11;
    text-transform: capitalize;
  }

  .text a {
    background: rgba(1, 1, 1, 0.9);
    width: fit-content;
    margin: auto;
    padding: 10px;
    border: 1px solid white;
  }
  .text:hover a {
    font-weight: 600;
    background: white;
    color: black;
  }

  @media only screen and (max-width: 800px) {
    section {
      height: 100vh;
    }
    .spine-container {
      top: 0px;
    }
    .spine-container .spine-left li,
    .spine-container .spine-right li {
      margin-top: 0px;
      opacity: 1;
      animation-name: open-spine;
      animation-duration: 0s;
      animation-fill-mode: forwards;
    }

    .text {
      font-size: 24px;
      position: absolute;
      vertical-align: middle;
      left: 0px;
      right: 0px;
      text-align: center;
      display: inline-grid;
      align-items: baseline;
      height: auto;
      align-content: space-evenly;
    }
    .mySlides img {
      padding: 20px;
      height: 100%;
      margin-bottom: 40px;
    }
    .text a {
      background: rgba(1, 1, 1, 0.5);
      width: fit-content;
      margin: auto;
      padding: 10px;
      border: 1px solid white;
    }
  }
</style>
