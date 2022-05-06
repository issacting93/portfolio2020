<section class="profile-container" id="about">
  <div class="col-01">
    <img class="my-photo" src="images/my-photo.jpg" alt="" />
  </div>
  <div class="col-01">
    <div class="profile-title">I do a little more than just design.</div>
    <div class="description" data-text="I do a little more than just design.">
      Skills - UX . UI . Scifi UI . 3D . Music . Motion . Frontend development .
      <br />

      Software - Blender . Unreal . AfterEffects . Html . Css .
      <br />
    </div>
    <br />
    <br />
    <div class="description">
      I also share ideas sometimes,
      <br />
      here are some of the sharings I have done.
      <br />
      <a href="https://youtu.be/rmX55ODcYeI">
        - Dating Tips 101 - A talk on CX
      </a>
      <br />
      <a href="https://youtu.be/ui2zG7kZxj4">
        - The future of UX - Why you should start a religion
      </a>
    </div>
  </div>
</section>

<style>
  a:hover {
    text-decoration: underline;
  }
  .profile-container {
    max-width: 1500px;
    display: flex;
    margin: auto;
    margin-top: 100px;
    margin-bottom: 100px;
    padding: 100px;
    align-items: center;
  }
  .col-01 {
    width: 50%;
    position: relative;
    padding: 40px;
  }
  .my-photo {
    max-height: 100%;
    width: 100%;
  }
  .profile-title {
    color: white;
    font-family: "Playfair Display";
    font-size: 32px;
    font-weight: 600;
    text-shadow: 2px 2px #05261285;
    transition: all 1s;
    padding-bottom: 10px;
  }

  .description {
    color: white;
    text-shadow: 2px 2px #05261285;
    transition: all 1s;
  }

  .profile-title::before {
    text-shadow: 2px 5px #3d0cee85;
  }
  .profile-title::after {
    text-shadow: 2px 5px #3d0cee85;
  }

  .profile-title::before {
    content: attr(data-text);
    position: absolute;
    left: -1.5px;
    text-shadow: 1.5px 0 #69cad1;

    animation: glitch1 0.8s infinite linear alternate-reverse;
  }

  .profile-title:after {
    content: attr(data-text);
    position: absolute;
    left: 1.5px;
    text-shadow: -1.5px 0 #ef1751;
    background-color: white;
    animation: glitch2 1s infinite linear alternate-reverse;
  }

  @keyframes glitch1 {
    0% {
      clip-path: inset(5% 0 15% 0);
    }
    20% {
      clip-path: inset(61% 0 9% 0);
    }
    40% {
      clip-path: inset(5% 0 81% 0);
    }
    60% {
      clip-path: inset(21% 0 52% 0);
    }
    80% {
      clip-path: inset(11% 0 70% 0);
    }
    100% {
      clip-path: inset(68% 0 6% 0);
    }
  }

  @keyframes glitch2 {
    0% {
      clip-path: inset(82% 0 9% 0);
    }
    20% {
      clip-path: inset(31% 0 44% 0);
    }
    40% {
      clip-path: inset(49% 0 11% 0);
    }
    60% {
      clip-path: inset(6% 0 85% 0);
    }
    80% {
      clip-path: inset(40% 0 37% 0);
    }
    100% {
      clip-path: inset(90% 0 3% 0);
    }
  }
  @media only screen and (max-width: 800px) {
    .my-photo {
      max-height: 100%;
      width: 100%;
    }
    .profile-container {
      max-width: 1500px;
      display: flex;
      margin: auto;
      padding: 100px;
      align-items: center;
      flex-direction: column;
    }
    .col-01 {
      width: 100%;
      text-align: center;
      height: 100%;
      vertical-align: middle;

      padding: 40px;
    }
    .profile-container {
      padding: 0px;
      height: auto;
    }
  }
</style>
