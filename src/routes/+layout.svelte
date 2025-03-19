<script lang="ts">
	import '../app.css';
	import Footer from '$lib/components/footer.svelte';
	import Header from '$lib/components/header.svelte';
	let { children } = $props();
</script>

<svelte:head>
	<title>EigerX</title>
	<meta name="viewport" content="width=device-width, initial-scale=1.0" />
</svelte:head>

<!-- <div
	class="relative flex min-h-screen w-full flex-col overflow-y-hidden border border-[var(--color-general)] px-4 pt-4 pb-4 shadow-[0_4px_10px_rgba(0,0,0,0.16)] md:px-10"
>
	<div class="fixed inset-0 z-0 h-[56%] bg-[var(--color-primary)] sm:h-[65%] md:h-[69%]">
		<img src="/bg.svg" alt="Gradient overlay" class="h-full w-full object-cover" />
	</div>
	<div class="fixed inset-0 top-[56%] z-0 h-1/2 sm:top-[65%] md:top-[69%]">
		<img src="/bg-2.svg" alt="Bottom gradient overlay" class="h-full w-full object-cover" />
	</div>

	<div class="relative z-10 flex flex-grow flex-col">
		<Header />
		<div class="flex-grow">
			{@render children()}
		</div>
		<Footer />
	</div>
</div> -->
<div
	class="relative flex min-h-screen w-full flex-col overflow-hidden border border-[var(--color-general)] px-4 pt-4 pb-4 shadow-[0_4px_10px_rgba(0,0,0,0.16)] md:px-10"
>
	<!-- Додати базовий зелений фон за всім для запобігання будь-яких просвітів -->
	<div
		class="fixed top-0 right-0 bottom-0 left-0 -z-10 min-h-[100vh] min-w-[100vw] bg-[var(--color-primary)]"
	></div>

	<!-- Фонові елементи з розширеним розміром, щоб уникнути просвітів -->
	<div
		class="fixed top-[-10px] right-[-10px] bottom-[auto] left-[-10px] z-0 h-[60%] bg-[var(--color-primary)] sm:h-[65%] md:h-[69%]"
	>
		<img
			src="/bg.svg"
			alt="Gradient overlay"
			class="h-[calc(100%+20px)] w-[calc(100%+20px)] object-cover"
		/>
	</div>

	<div
		class="fixed top-[55%] right-[-10px] bottom-[-10px] left-[-10px] z-0 min-h-[50%] sm:top-[64%] md:top-[68%]"
	>
		<img
			src="/bg-2.svg"
			alt="Bottom gradient overlay"
			class="h-[calc(100%+20px)] w-[calc(100%+20px)] object-cover"
		/>
	</div>

	<div class="relative z-10 flex flex-grow flex-col">
		<Header />
		<div class="flex-grow">
			{@render children()}
		</div>
		<Footer />
	</div>
</div>
