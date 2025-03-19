<header class="p-5 pb-0">
	<div class="mb-[100px] flex items-center justify-between sm:mb-[150px] md:mb-0">
		<!-- Logo -->
		<div class="h-[32px] w-[110px] sm:h-[40px] sm:w-[140px]">
			<img
				src="/logo.svg"
				alt="Logo"
				class="h-full max-h-full w-full max-w-full object-contain"
				loading="lazy"
			/>
		</div>

		<!-- Avatars -->
		<div class="flex space-x-[-8px]">
			{#each [1, 2, 3] as img, index}
				<img
					src={`/user-${img}.svg`}
					alt={`User ${img} avatar`}
					style="z-index: ${3 - index};"
					class={`h-10 w-10 cursor-pointer rounded-full border-2 border-[var(--color-general)] transition-all duration-300  
                    ease-out hover:translate-y-[-4px] hover:scale-110 hover:rotate-[-2deg] hover:border-[var(--color-primary)] hover:shadow-lg 
                    sm:h-14 sm:w-14`}
				/>
			{/each}
		</div>
	</div>
</header>
