<script>
	import { drawerIsToggled } from '../Store.js';
</script>

<section
	class="sm:h-full h-auto w-full sm:w-auto p-5 sm:border-r border-b border-stone-200 flex sm:flex-col justify-between items-center sticky top-0 bg-white"
>
	<div class="flex-1">
		<a href="https://darkhorizonrobotics.netlify.app"
			><img src="/logo.png" alt="logo" class="w-20 h-auto" /></a
		>
	</div>

	<!-- social media links (big version) -->
	<div class="sm:h-36 sm:w-full w-52 items-center sm:flex sm:flex-col justify-between hidden">
		<a
			href="https://instagram.com/darkhorizonrobotics?igshid=ZDdkNTZiNTM="
			target="_blank"
			rel="noreferrer"><i class="fa-brands fa-instagram text-xl" /></a
		>
		<span class="font-bold"> · </span>
		<a
			href="https://www.facebook.com/profile.php?id=100091507760678&mibextid=ZbWKwL"
			target="_blank"
			rel="noreferrer"><i class="fa-brands fa-facebook text-xl" /></a
		>
		<span class="font-bold"> · </span>
		<a href="#_"><i class="fa-brands fa-youtube text-xl" /></a>
	</div>

	<!-- menu -->
	<div class="flex flex-col sm:flex-1 justify-end">
		<button
			class="inline-flex items-center justify-center px-4 py-2 text-base font-medium leading-6 text-gray-600 whitespace-no-wrap bg-white border border-gray-200 rounded-md shadow-sm hover:bg-gray-50 focus:outline-none focus:shadow-none transition-colors"
			on:click={() => {
				$drawerIsToggled = !$drawerIsToggled;
			}}
		>
			<i class="fa-solid fa-bars text-2xl" />
		</button>
	</div>
</section>
