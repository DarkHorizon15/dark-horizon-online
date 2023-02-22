<script>
	let drawerIsToggled = true;
	const toggleDrawer = () => {
		drawerIsToggled = !drawerIsToggled;
	};
</script>

<!-- page wrapper -->
<section class="flex sm:flex-row flex-col h-[100vh]">
	<section
		class="sm:h-full h-auto w-full sm:w-auto p-5 sm:border-r border-b border-stone-200 flex sm:flex-col justify-between items-center"
	>
		<div class="flex-1">
			<img src="/logo.png" alt="logo" class="w-20 h-auto" />
		</div>

		<!-- social media links (big version) -->
		<div class="sm:h-36 sm:w-full w-52 items-center sm:flex sm:flex-col justify-between hidden">
			<a href="#_"><i class="fa-brands fa-instagram text-xl" /></a>
			<span class="font-bold"> · </span>
			<a href="#_"><i class="fa-brands fa-twitter text-xl" /></a>
			<span class="font-bold"> · </span>
			<a href="#_"><i class="fa-brands fa-youtube text-xl" /></a>
		</div>

		<!-- menu -->
		<div class="flex flex-col sm:flex-1 justify-end">
			<button
				class="inline-flex items-center justify-center px-4 py-2 text-base font-medium leading-6 text-gray-600 whitespace-no-wrap bg-white border border-gray-200 rounded-md shadow-sm hover:bg-gray-50 focus:outline-none focus:shadow-none transition-colors"
				on:click={toggleDrawer}
			>
				<i class="fa-solid fa-bars text-2xl" />
			</button>
		</div>
	</section>

	<!-- overlay -->
	<!-- svelte-ignore a11y-click-events-have-key-events -->
	<section
		class="absolute w-full h-full z-20 bg-slate-900 transition-all ease-in-out {!drawerIsToggled
			? 'opacity-0 pointer-events-none'
			: 'opacity-25 pointer-events-auto'}"
		on:click={toggleDrawer}
	/>
	
	<!-- sidebar -->
	<aside
		class="transform top-0 right-0 w-96 bg-white fixed h-full overflow-auto ease-in-out transition-all border-l border-stone-200 duration-300 z-30 {drawerIsToggled
			? '-translate-x-0'
			: 'translate-x-full'}"
	>
	<div class="w-full p-5">
		<h1>Content</h1>
	</div>
	</aside>
</section>
