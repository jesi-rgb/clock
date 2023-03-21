<script>
	let scale = 35;
	let textOffset = 20;
</script>

<div class="flex justify-center">
	<svg width="500" height="500" viewBox="-50 -50 100 100">
		{#each [0, 5, 10, 15, 20, 25, 30, 35, 40, 45, 50, 55] as minute, hour}
			<line class="major stroke-stone-500" y1="35" y2="45" transform="rotate({30 * minute})" />
			<text
				class="fill-stone-600 font-serif"
				text-anchor="middle"
				font-size="8"
				dominant-baseline="middle"
				transform="translate({-Math.sin(textOffset * minute) * scale}, {-Math.cos(
					textOffset * minute
				) * scale})">{((hour + 11) % 12) + 1}</text
			>
			{#each [1, 2, 3, 4] as offset}
				<line
					class="minor stroke-stone-300"
					y1="40"
					y2="45"
					transform="rotate({6 * (minute + offset)})"
				/>
			{/each}
		{/each}
	</svg>
</div>
