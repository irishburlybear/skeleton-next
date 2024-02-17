<script>
	let { footer, fullHeader, fullFooter, header, leftSide, rightSide, children } = $props();
	console.log(header);
</script>

<div class="flex h-dvh w-dvw flex-col overflow-y-auto bg-red-400">
	<!-- <div class=""> -->
	{#if fullHeader}
		{@render fullHeader()}
	{/if}
	<!-- </div> -->

	<div class="flex h-full overflow-y-auto">
		{#if leftSide}
			<div class="flex h-full min-w-min flex-col overflow-hidden overflow-y-auto p-1">
				{@render leftSide()}
			</div>
		{/if}
		<div class="flex w-full flex-col">
			<!-- <div class=""> -->
			{#if header}
				{@render header()}
			{/if}
			<!-- </div> -->
			<div class="h-full overflow-y-auto">
				{#if children}
					{@render children()}
				{/if}
			</div>
		</div>
		{#if rightSide}
			<div class="flex h-full min-w-min flex-col overflow-hidden overflow-y-auto p-1">
				{@render rightSide()}
			</div>
		{/if}
	</div>

	<!-- <div class=""> -->
	{#if fullFooter}
		{@render fullFooter()}
	{/if}
	<!-- </div> -->
</div>
