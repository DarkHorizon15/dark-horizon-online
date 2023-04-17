<script>
	import '../app.css';
	import { drawerIsToggled } from '../Store.js';
	import Sidemenu from '../lib/Sidemenu.svelte';
</script>

<link
	rel="stylesheet"
	href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.3.0/css/all.min.css"
	integrity="sha512-SzlrxWUlpfuzQ+pcUCosxcglQRNAq/DZjVsC0lE40xsADsfeQoEypE+enwcOiGjk/bSuGGKHEyjSoQ1zVisanQ=="
	crossorigin="anonymous"
	referrerpolicy="no-referrer"
/>

<!-- page wrapper -->
<section
	class="flex sm:flex-row flex-col h-[100vh] {!$drawerIsToggled
		? 'overflow-auto'
		: 'overflow-hidden'}"
>
	<Sidemenu />

	<slot />
	<!-- overlay -->
	<!-- svelte-ignore a11y-click-events-have-key-events -->
	<section
		class="absolute w-full h-full z-20 bg-slate-900 transition-all ease-in-out {!$drawerIsToggled
			? 'opacity-0 pointer-events-none'
			: 'opacity-30 pointer-events-auto'}"
		on:click={() => {
			$drawerIsToggled = !$drawerIsToggled;
		}}
	/>

	<!-- sidebar -->
	<aside
		class="transform top-0 right-0 sm:w-96 w-4/6 bg-white fixed h-full overflow-auto ease-in-out transition-all border-l border-stone-200 duration-300 z-30 {$drawerIsToggled
			? '-translate-x-0'
			: 'translate-x-full'}"
	>
		<div class="w-full p-10">
			<h1 class="text-2xl">Explore Our Site</h1>
			<ul class="mt-10">
				<li class="py-2"><a href="#_">About Us</a></li>
				<li class="py-2"><a href="#_">Sponsorship Information</a></li>
				<li class="py-2"><a href="#_">Accomplishments</a></li>
				<li class="py-2"><a href="#_">About VEX</a></li>
			</ul>
		</div>
	</aside>
</section>
