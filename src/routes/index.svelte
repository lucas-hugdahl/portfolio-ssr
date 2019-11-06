<script>
	import Header from "./home/Header.svelte";
	import About from "./home/About.svelte";
	import Skills from "./home/Skills.svelte";
	import Work from "./home/Work.svelte";
	import workList from "./home/data/work";
	import skillsList from "./home/data/skills";
</script>

<style>
	
</style>

<svelte:head>
	<title>Lucas Hugdahl - Home</title>
</svelte:head>

<Header />
<About />
<Skills skills={skillsList}/>
<Work work={workList}/>
