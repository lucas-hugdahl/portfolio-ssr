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

<style type="text/scss">
	.main {
		position: relative;
		min-height: 100vh;
		min-width: 100vw;
		overflow: hidden;
		.bg {
			position: absolute;
			top: 0;
			left: 0;
			width: 100%;
			height: 100%;
			min-height: 1000vh;
			transition: height .3s ease-in-out;
			filter: blur(6px);
			transform: scale(1.1);
			background-image: url("images/bg.jpg");
			background-size: cover;
			background-position: center;
			z-index: -1;
		}

		.content{
			z-index: 1;
		}
	}
</style>

<main class="main py-lg-6">
	<div class="bg"></div>
	<div class="container-main content bg-white">
		<Nav {segment}/>
		<slot></slot>
		<Contact/>
	</div>
</main>