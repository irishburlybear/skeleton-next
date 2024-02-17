<script>
	let {
		footer,
		fullHeader,
		fullFooter,
		header,
		leftSide,
		rightSide,
		children,
		leftSideClass,
		appShellClass,
		fullHeaderClass,
		headerClass,
		rightSideClass,
		footerClass,
		fullFooterClass,
		defaultClass
	} = $props();
	console.log(header);
</script>

<div class={`${appShellClass} flex h-dvh w-dvw flex-col overflow-y-auto`}>
	<div class={fullHeaderClass}>
		{#if fullHeader}
			{@render fullHeader()}
		{/if}
	</div>

	<div class="flex h-full overflow-y-auto">
		{#if leftSide}
			<div
				class={`${leftSideClass} flex h-full min-w-min flex-col overflow-hidden overflow-y-auto`}
			>
				{@render leftSide()}
			</div>
		{/if}
		<div class="flex w-full flex-col">
			{#if header}
				<div class={headerClass}>
					{@render header()}
				</div>
			{/if}
			{#if children}
				<div class={`${defaultClass} h-full overflow-y-auto`}>
					{@render children()}
				</div>
			{/if}
			{#if footer}
				<div class={footerClass}>
					{@render footer()}
				</div>
			{/if}
		</div>
		{#if rightSide}
			<div
				class={`${rightSideClass}flex h-full min-w-min flex-col overflow-hidden overflow-y-auto`}
			>
				{@render rightSide()}
			</div>
		{/if}
	</div>

	<div class={fullFooterClass}>
		{#if fullFooter}
			{@render fullFooter()}
		{/if}
	</div>
</div>
