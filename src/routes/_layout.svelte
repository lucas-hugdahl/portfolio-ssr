<script>
	import AOS from "aos"
	import {onMount} from "svelte"
	import Nav from '../components/Nav.svelte';
	import Contact from '../components/Contact.svelte';
	export let segment;

	onMount(async () => {
		AOS.init();
	});
</script>

<style>
	.main {
		position: relative;
		min-height: 100vh;
		min-width: 100vw;
		overflow: hidden;
	}
	.bg {
		position: absolute;
		top: 0;
		left: 0;
		width: 100vw;
		height: 100vh;
		filter: blur(8px);
		transform: scale(1.1);
		min-height: 1000vh;
		background-image: url("images/bg-new.jpg");
		background-position: center;
		/* background-attachment: fixed; */
		z-index: -1;
	}
	.content{
		z-index: 1;
		box-shadow: 0 0 10px 5px rgba(0, 0, 0, 0.185);
	}
</style>

<main class="main py-lg-6">
	<div class="bg"></div>
	<div class="container-main content bg-white">
		<!-- <Nav {segment}/> -->
		<slot></slot>
		<Contact/>
	</div>
</main>