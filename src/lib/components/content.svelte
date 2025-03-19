<script>
	let searchQuery = '';
	const helpTopics = [
		{ title: 'In-game bonuses and free spins', link: '#' },
		{ title: 'Crypto deposit still not credited?', link: '#' },
		{ title: 'EigerX VIP program overview', link: '#' },
		{ title: 'Achievements and awards', link: '#' }
	];
	$: filteredTopics = searchQuery
		? helpTopics.filter((topic) => topic.title.toLowerCase().includes(searchQuery.toLowerCase()))
		: helpTopics;
</script>

<main class="flex flex-1 grow flex-col">
	<div class="mb-3 px-5 sm:mb-10 md:my-20">
		<h1
			class="font-sfpro text-[32px] leading-[38px] tracking-[0] text-[var(--color-white)] opacity-70 md:pb-10 md:text-7xl"
		>
			Hello there
		</h1>
		<h2
			class="font-sfpro text-[32px] leading-[38px] tracking-[0] text-[var(--color-white)] md:text-7xl"
		>
			How can we help?
		</h2>
	</div>

	<div class="flex grow-1 flex-col gap-3 rounded-lg md:gap-8">
		<!-- Message button -->
		<button
			type="submit"
			aria-label="Send us a message"
			class="relative flex w-full cursor-pointer items-center justify-between rounded-[10px] border border-[var(--color-primary)] bg-[var(--color-dark-gray)] px-5 py-4
               transition-all duration-300 ease-in-out
               hover:bg-[var(--color-gray)]/10 hover:shadow-sm hover:shadow-[#4EEAB1]/40
               "
		>
			<div>
				<p
					class="font-inter text-start text-sm leading-[21px] font-semibold text-[var(--color-white)]"
				>
					Send us a message
				</p>
				<span
					class="font-inter text-start text-sm leading-[21px] font-normal text-[var(--color-gray)]"
				>
					We typically reply within a day
				</span>
			</div>
			<div class="absolute top-1/2 right-5 -translate-y-1/2">
				<img src="src/images/send.svg" alt="Send Icon" class="object-contain" loading="lazy" />
			</div>
		</button>

		<!-- Contetent container -->
		<div
			class="overflow-hidden rounded-[10px] border border-[var(--color-general)] bg-[var(--color-general-black)] p-2"
		>
			<!-- Search bar -->
			<div class="relative flex items-center pb-2">
				<input
					type="text"
					placeholder="Search for help"
					bind:value={searchQuery}
					class="font-inter placeholder-opacity-100 w-full rounded-lg bg-[var(--color-dark-gray)] px-[12px] py-[10px] text-sm leading-[21px] font-semibold text-[var(--color-white)] placeholder-[var(--color-light-gray)] outline-none"
				/>
				<button
					class="absolute top-1/2 right-3 -translate-y-1/2 cursor-pointer"
					aria-label="Search"
					on:click={() => (searchQuery = searchQuery)}
				>
					<img
						src="/src/images/search.svg"
						alt="Search Icon"
						class="h-4 w-4 translate-y-[-3px] transform object-contain"
					/>
				</button>
			</div>

			<!-- Help topics -->

			<div>
				{#if filteredTopics.length === 0}
					<div
						class="font-inter px-3 py-[10px] text-center text-sm leading-[21px] text-[var(--color-light-gray)]"
					>
						No results found for "{searchQuery}"
					</div>
				{:else}
					{#each filteredTopics as topic, i}
						<div
							class="flex cursor-pointer items-center justify-between px-3 py-[10px] transition hover:rounded-lg hover:bg-[var(--color-dark-gray)]"
						>
							<div class="font-inter text-sm leading-[21px] text-[var(--color-light-gray)]">
								{topic.title}
							</div>
							<div class="flex-shrink-0">
								<img
									src="src/images/right-arrow.svg"
									alt="Arrow Icon"
									class="h-4 w-4 object-contain"
								/>
							</div>
						</div>
					{/each}
				{/if}
			</div>
		</div>
	</div>
</main>
