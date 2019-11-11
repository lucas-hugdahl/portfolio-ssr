<script>
  export let image;
  export let brand;
  export let url;
  export let skills;
</script>

<style type="text/scss">
  @import "../../../scss/base/variables";

  .grid {
    --grid-height: 16rem;
    text-decoration: none;
    box-shadow: 0 0 10px 2px rgba(0, 0, 0, 0.259);
    transition: all 0.2s ease-in-out;
    box-sizing: border-box;
    display: grid;
    max-width: 100%;
    grid-template-areas:
      "image   image"
      "company  company"
      "skills  skills";
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 16rem 50px 50px;
    
    
    @media (min-width: map-get($breakpoints, lg)) {
      grid-template-rows: 23rem 50px;
      grid-template-areas:
      "image   image"
      "company  skills";
    }
  }

  .grid:hover {
    transform: translateY(-10px);
    cursor: pointer;
  }

  .image {
    grid-area: image;
    background-size: cover;
    background-position: center;
  }

  .logo, .name {
    grid-area: company;
    align-self: center;
  }


  .skill, .logo {
    height: 25px;
  }

  .skills {
    grid-area: skills;
    align-self: center;
    display: grid;
    grid-auto-flow: column;
    align-items: center;
    justify-content: start;
    @media (min-width: map-get($breakpoints, lg)) {
      justify-content: end;
    }
  }
</style>

<!-- {{image}} -->
<div
  class="work-card mb-6"
  target="_blank"
  onclick={() => {
    window.open(url, '_blank');
  }}
  data-aos="fade-up"
  data-aos-anchor-placement="top-center"
  role="link">
  <div class="grid">
    <div class="image" style={`background-image: url('${image}')`} />

    {#if brand.includes('images/logos/')}
    <img class="logo ml-2" alt={brand} src={brand} />
    {:else}
      <h3 class="name w-100 m-0 ml-2">{brand}</h3>
    {/if}
    
    <div class="skills px-2">
      {#each skills as skill, skillIndex}
        <img
          class="skill mr-1 mr-lg-2"
          src={skill.image}
          alt={skill.name}
          data-aos="fade-up"
          data-aos-delay={skillIndex * 100} />
      {/each}
    </div> 
  </div>
</div>
