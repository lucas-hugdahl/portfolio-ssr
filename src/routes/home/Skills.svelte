<script>
  import SkillCard from "./components/SkillCard.svelte";
  export let skills;

  let skillRows = [
    [
      skills.vue,
      skills.react,
      skills.svelte
    ],
    [
      skills.sass,
      skills.bash,
      skills.bootstrap
    ],
    [
      skills.gulp,
      skills.webpack,
      skills.rollup  
    ],
    [
      skills.mssql,
      skills.mysql,
      skills.mongo
    ],
    [
      skills.zesty, 
      skills.babylon,
      skills.three,
    ],
    [
      skills.git, 
      skills.wordpress,
      skills.twig
    ],
    [
      skills.jquery,
      skills.npm,
      skills.aws    
    ],
    [
      skills.html,
      skills.css,
      skills.js    
    ],
    [
      skills.figma,
      skills.photoshop,
      skills.illustrator
    ]
     
  ]
</script>
<style type="text/scss">
  @import "../../scss/base/variables";
  .title {
    text-align: center;
  }
  .icons {
    --cols: 3;
    display: grid;
    grid-template-columns: repeat(var(--cols), 1fr);
    justify-items: center;   
  }
</style>

<section class="skills px-lg-5 px-2">
  <h1 class="title py-4">SKILLS</h1>
  <div class="icons">
    {#each skillRows as rowItem, rowIndex}
      <!-- <div class="row {rowIndex % 2 ? 'row--flip' : ''}"> -->
        {#each rowItem as col, colIndex}
              <SkillCard
                image={col.image}
                name={col.name}
                url="{col.url}"
                fadeDelay="{(colIndex + 1) * 100}"
              />
        {/each}
      <!-- </div> -->
    {/each}
  </div>
</section>