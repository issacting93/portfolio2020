<script>
  import RadialInterface from "./RadialInterface.svelte";
</script>

<section class="section-03" id="case-studies">
  <div class="about-container">
    <div class=" title">
      Designing and maintaining <br /> meaningful User experiences
    </div>

    <div class="svg-padding">
      <svg
        width="30"
        height="1"
        viewBox="0 0 30 1"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <line y1="0.5" x2="30" y2="0.5" stroke="white" />
      </svg>
    </div>
    <div class="about-text">
      For 4 years now, I had the pleasure of working in MNCs and Goverment
      services to provide design and creative technological service to build
      products ranging from small gamification projects to large scale Design
      Systems.
      <br /> I’ve been involved in variety of projects in the area of prototyping,
      user experience design, research and design operations.
    </div>
    <br />

    <div class="svg-padding">
      <svg
        width="1"
        height="40"
        viewBox="0 0 1 120"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <line x1="0.5" y1="2.18557e-08" x2="0.499995" y2="120" stroke="white" />
      </svg>
    </div>
    <a class="resume-tag" href="/images/Issac Ting Resume.pdf" download>
      <svg
        width="24"
        height="24"
        viewBox="0 0 24 24"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          fill-rule="evenodd"
          clip-rule="evenodd"
          d="M11.25 7.5V13.307L9.88327 11.9403L8.82261 13.0009L11.4697 15.648L12 16.1783L12.5303 15.648L15.1774 13.0009L14.1167 11.9403L12.75 13.307V7.5H19C20.3807 7.5 21.5 8.61929 21.5 10V17C21.5 18.3807 20.3807 19.5 19 19.5H5C3.61929 19.5 2.5 18.3807 2.5 17V10C2.5 8.61929 3.61929 7.5 5 7.5H11.25Z"
          fill="white"
        />
        <path d="M12 4.5V7.5" stroke="white" stroke-width="1.5" />
      </svg>

      Download Resume</a
    >
  </div>
</section>

<style>
  section {
    height: auto;
    padding-top: 100px;
    background-color: rgb(26, 26, 26);
  }
  .svg-padding {
    margin-top: 20px;
    margin-bottom: 20px;
  }
  .title {
    display: flex;
    flex-direction: column;
    position: relative;
    height: 100%;
    top: 10px;
    text-align: center;
    color: white;
    margin-bottom: 20px;
  }
  .about-text {
    max-width: 600px;
    font-weight: 400;
    font-size: 16px;
    line-height: 24px;
    text-align: center;
    color: white;
    margin: auto;
  }
  .about-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  section.section-03 {
    display: flex;
    justify-content: center;
    align-items: center;
    font-family: "Barlow";
    font-style: normal;
  }
  a.resume-tag {
    display: flex;
    flex-direction: row-reverse;
    justify-content: center;
    align-content: center;
    align-items: center;
    transition: all 0.2s;
  }

  a.resume-tag:hover {
    color: rgb(235, 87, 87);
  }
  a.resume-tag svg {
    margin: 0px 10px;
  }
  @media only screen and (max-width: 800px) {
    .about-container {
      display: flex;
      height: 100%;
      flex-direction: column;
      align-items: center;
      justify-content: center;

      padding: 20px;
    }

    .about-text {
      margin: auto;
      width: calc(100vw - 80px);
    }
  }
</style>
