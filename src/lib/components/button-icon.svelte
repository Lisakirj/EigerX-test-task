<script>
	export let activeTab;
	export let tabName;
	export let iconSrc;
	export let activeIconSrc;
	export let onClick;
</script>

<button
	on:click={onClick}
	class="group flex flex-1 cursor-pointer flex-col items-center gap-[8px] md:flex-row"
>
	<div class="transition-transform duration-300 hover:scale-110">
		<img
			src={activeTab === tabName ? activeIconSrc : iconSrc}
			alt={tabName}
			class="h-6 w-6 object-contain transition-all duration-300 group-hover:opacity-80"
			loading="lazy"
		/>
	</div>
	<div
		class="font-inter text-sm leading-[21px] transition-all duration-300 {activeTab === tabName
			? 'text-[var(--color-primary)]'
			: 'text-[var(--color-light-gray)]'} group-hover:text-[var(--color-primary)]"
	>
		{tabName}
	</div>
</button>
