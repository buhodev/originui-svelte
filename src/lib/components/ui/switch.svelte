<script lang="ts">
	import { cn } from '$lib/utils.js';

	import { Switch as SwitchPrimitive } from 'bits-ui';

	let {
		checked = $bindable(false),
		class: className,
		ref = $bindable(null),
		...restProps
	}: SwitchPrimitive.RootProps = $props();
</script>

<SwitchPrimitive.Root
	bind:ref
	bind:checked
	class={cn(
		'peer inline-flex h-6 w-10 shrink-0 cursor-pointer items-center rounded-full border-2 border-transparent transition-colors focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 focus-visible:ring-offset-background disabled:cursor-not-allowed disabled:opacity-50 data-[state=checked]:bg-primary data-[state=unchecked]:bg-input',
		className
	)}
	{...restProps}
>
	<SwitchPrimitive.Thumb
		class={cn(
			'pointer-events-none block size-5 rounded-full bg-background shadow-sm shadow-black/[.04] ring-0 transition-transform duration-300 [transition-timing-function:cubic-bezier(0.16,1,0.3,1)] data-[state=checked]:translate-x-4 data-[state=unchecked]:translate-x-0 rtl:data-[state=checked]:-translate-x-4'
		)}
	/>
</SwitchPrimitive.Root>
