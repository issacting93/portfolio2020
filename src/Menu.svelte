<script>
  import CloseBtn from "./CloseBtn.svelte";
  import MenuBtn from "./MenuBtn.svelte";
  import SpineMenu from "./SpineMenu.svelte";
  import BorderR from "./BorderR.svelte";
  import BorderL from "./BorderL.svelte";
  let OpenMenu = false;
  let LeftArrow = "images/left-arrow.svg";
  window.addEventListener("load", function () {
    // Get the container element
    var btnContainer = document.getElementById("menu");

    // Get all buttons with class="btn" inside the container
    var btns = document.getElementsByClassName("btn");

    // Loop through the buttons and add the active class to the current/clicked button
    console.log("click");
    for (var i = 0; i < btns.length; i++) {
      btns[i].addEventListener("click", function () {
        console.log("click");
        var current = document.getElementsByClassName("active");

        current[0].className = current[0].className.replace("active", "");
        console.log(current[0].className);
        this.className += " active";
      });
    }
  });
</script>

<div class="menu-container">
  <button class="toggle-menu" on:click={() => (OpenMenu = !OpenMenu)}>
    {#if OpenMenu}
      <div class="close-btn"><CloseBtn /></div>
    {:else}
      <div class="open-btn"><BorderL /> <MenuBtn /> <BorderR /></div>
    {/if}
  </button>
  {#if OpenMenu}
    <SpineMenu />
  {/if}
</div>

<style>
  .menu-container {
    background-color: rgb(26 26 26);
  }

  .open-btn {
    opacity: 0.7;
    transition: all 1s;
    cursor: pointer;
    display: flex;
    align-content: space-around;
    align-items: center;
  }

  .open-btn:hover {
    opacity: 1;
  }
  button.btn {
    font-family: "Barlow";
    font-size: 16px;
    font-weight: 100;
    border-radius: 12px;
    padding: 2px;
    background: none;
    border: 0px;
    right: 0px;
    margin: 10px 20px;
    height: auto;
  }
  .btn a {
    margin: 8px;
  }
  .btn:hover {
    border: 1px #ff3434 solid;
    color: #ff3434;
  }
  .btn.active {
    border: 1px white solid;
    color: #ff3434;
    background-color: rgba(1, 1, 1, 0.5);
  }
  @keyframes slide-out {
    0% {
      transform: translate(20vw, 0);
    }
    100% {
      transform: translate(0, 0);
    }
  }

  @keyframes rotate-in {
    0% {
      transform: rotate(-90deg);
    }
    100% {
      transform: rotate(90deg);
    }
  }

  @keyframes slide-up {
    0% {
      height: 0px;
    }
    100% {
      height: 100vh;
    }
  }
  .close-btn {
    animation-name: rotate-in;
    animation-duration: 0.3s;
    animation-fill-mode: forwards;
    cursor: pointer;
  }
  .toggle-menu {
    background: none;
    border: 0px;
    display: flex;
  }
  .menu {
    animation-name: slide-up;
    animation-duration: 0.3s;
    animation-fill-mode: forwards;
    max-height: 300px;
    transition: all 1s;
  }

  .menu-container {
    background-color: rgb(26 26 26);
    transition: all 1s;
    margin: 0px;
    padding: 0px;
    display: flex;
    flex-direction: column;
    z-index: 130;
    position: fixed;
    top: 0px;
    right: 0px;
    width: 100%;
    align-items: center;
  }

  @media screen and (max-width: 800px) {
    .menu-container {
      width: 100%;
      top: 0px;
      min-height: fit-content;
    }
    section {
      height: 100%;
    }

    button.btn {
      margin: 10px 0px;
    }

    .toggle-menu {
      position: fixed;
      background-color: rgba(1, 1, 1, 0.9);
      border: 0px;
      padding: 0px;
      top: 0px;
      z-index: 10;
      margin: 0px;
      width: 100%;
      border-radius: 0px;
      display: flex;
      justify-content: center;
    }

    .menu {
      max-height: none;
      display: flex;
      flex-direction: column;
      text-align: left;
      align-items: flex-start;
      justify-content: flex-start;
      background-color: rgba(1, 1, 1, 0.97);
      animation-name: slide-up;
      animation-duration: 0.3s;
      top: 0px;
      animation-fill-mode: forwards;
      left: 0px;
      position: absolute;
      width: 100vw;
      padding: 40px;
      height: 100%;
    }
  }
</style>
