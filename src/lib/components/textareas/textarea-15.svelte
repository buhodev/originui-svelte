<script lang="ts">
	const uid = $props.id();
</script>

<div
	class="relative rounded-lg border border-input bg-background shadow-sm shadow-black/[.04] ring-offset-background transition-shadow focus-within:border-ring focus-within:ring-2 focus-within:ring-ring/30 focus-within:ring-offset-2 has-[:disabled]:cursor-not-allowed has-[:disabled]:opacity-50 [&:has(input:is(:disabled))_*]:pointer-events-none"
>
	<label for={uid} class="block px-3 pt-2 text-xs font-medium text-foreground">
		Textarea with inset label
	</label>
	<textarea
		id={uid}
		class="flex min-h-[70px] w-full bg-transparent px-3 pb-2 text-sm text-foreground placeholder:text-muted-foreground/70 focus-visible:outline-none"
	></textarea>
</div>
