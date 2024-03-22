<script>
  import ChartContainer from "./components/ChartContainer.svelte";
  import Header from "./components/Header.svelte";
  import Skills from "./components/Skills.svelte";
  import { skills } from "./data/skillTime";
</script>

<main>
  <div class="page">
    <div class="width-90">
      <Header headerText="Skills" />
      <Skills />
    </div>
  </div>

  <div class="page">
    <div class="width-90">
      <Header headerText="Skills Over Time" />
      <ChartContainer
        type={"lineChart"}
        chartProps={{
          chartWidth: 800,
          chartHeight: 500,
          data: skills,
          xVar: "Year",
          yVars: ["Skill"],
        }}
      />
    </div>
  </div>
</main>

<style>
  .page {
    display: flex;
    flex-flow: column;
    height: 100vh;
    justify-content: space-around;
  }

  .height {
    height: auto !important;
  }

  .center {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
  }

  .width-90 {
    width: 90%;
    margin: auto;
  }

  p {
    text-align: justify;
    width: 70%;
    margin: auto;
    text-justify: inter-word;
  }

  span {
    font-weight: 800;
  }

  img {
    width: 12rem;
    transition: 0.5s;
    margin: 2rem;
    padding: 2rem;
  }

  img:hover {
    scale: 110%;
  }
</style>
