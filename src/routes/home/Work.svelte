<script>
  import WorkCard from "./components/WorkCard.svelte";
  export let work;
</script>
<style type="text/scss">
  .work {
    position: relative;
  }
 .title {
    text-align: center;
  }
</style>

<section class="pb-3 work">
    <h1 class="title py-4">RECENT WORK</h1>
    <div class="px-2 px-lg-5">
      {#each work as project}
        <WorkCard 
          image={project.image}
          url={project.url}
          brand={project.brand}
          skills={project.skills}
        />
      {/each}
    </div>
</section>