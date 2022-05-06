<script>
  import Terrain from "./terrain.svelte";
  import GridComponent from "./SVGgridComponent.svelte";
  import MapIndicator from "./mapIndicator.svelte";
</script>

<section class="section-02" id="find-me">
  <div class="title">FIND ME</div>
  <div class="map-container">
    <div class="terrain-container">
      <div class="marker-container">
        <div class="marker-01">
          <a href="https://www.behance.net/zacting" target="_blank">
            <MapIndicator />
            Behance
          </a>
        </div>
        <div class="marker-04">
          <a
            href=" https://www.figma.com/community/file/1081845377665077907/SCIFI-KIT-01"
            target="_blank"
          >
            <MapIndicator />
            Scifi UI Kit
          </a>
        </div>
        <div class="marker-02">
          <a
            href=" https://glossy-ink-3c8.notion.site/UX-Resource-e6b1726d50d944db8156e756c2731094"
            target="_blank"
          >
            <MapIndicator />
            UX Resources</a
          >
        </div>
        <div class="marker-03">
          <a
            href=" https://www.linkedin.com/in/issac-ting-b489a98b/"
            target="_blank"
          >
            <MapIndicator />
            LinkedIn
          </a>
        </div>

        <div class="marker-04">
          <a
            href=" https://www.figma.com/community/plugin/1032111792919656443/Markers"
            target="_blank"
          >
            <MapIndicator />
            Marker Plugin
          </a>
        </div>
      </div>
      <Terrain />
      <GridComponent />
    </div>
  </div>
</section>

<style>
  .section-02 .terrain-container {
    display: none;
    transition: all 1s;
    max-width: 1200px;
  }

  .section-02:hover .terrain-container {
    display: block;
    opacity: 1;
  }

  .marker-container {
    display: flex;
    height: 100%;
    align-items: center;
    justify-content: space-between;
    padding: 40px;
  }

  .marker-01 {
    color: white;
    width: 100%;
    z-index: 11;
    width: auto;
    animation: fadein 0.2s ease-in forwards;
    animation-delay: 0.3s;
    margin-top: 20%;

    margin-left: 20%;
  }

  .marker-02 {
    color: white;
    z-index: 11;
    opacity: 0;
    animation: fadein 0.2s ease-in forwards;
    animation-delay: 1.3s;
    margin-top: -15%;
    margin-left: -20%;
  }

  .marker-03 {
    color: white;
    right: 0;
    z-index: 11;
    opacity: 0;
    animation: fadein 0.2s ease-in forwards;
    animation-delay: 0.9s;
    margin-top: -5%;
    margin-left: 10%;
  }

  .marker-04 {
    color: white;
    right: 0;
    z-index: 11;
    opacity: 0;
    animation: fadein 0.2s ease-in forwards;
    animation-delay: 0.9s;
    margin-top: 2.6%;
    margin-left: 10%;
  }
  .terrain-container {
    height: 100vh;
    width: 100vw;
    max-width: 1600px;
    margin: auto;
    position: absolute;
    left: 0px;
    overflow: hidden;
    right: 0px;
  }

  /* On smaller screens, decrease text size */
  @media only screen and (max-width: 960px) {
    .section-02 .terrain-container {
      display: block;
      transition: all 1s;
      max-width: 1200px;
    }
    .marker-01 {
      margin-top: -10%;
      margin-left: -2%;
    }

    .marker-02 {
      margin-top: -55%;
      margin-left: -2%;
    }

    .marker-03 {
      margin-top: 65%;
      margin-left: 0%;
    }
    .section-02:hover .terrain-container {
      display: block;
      opacity: 1;
    }
  }
</style>
