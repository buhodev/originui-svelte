<script lang="ts">
	import { RadioGroup, RadioGroupItem } from '$lib/components/ui/radio-group/index.js';

	let selectedValue = $state('on');
</script>

<div class="inline-flex h-9 rounded-lg bg-input/50 p-0.5">
	<RadioGroup
		bind:value={selectedValue}
		class="group relative inline-grid grid-cols-[1fr_1fr] items-center gap-0 text-sm font-medium after:absolute after:inset-y-0 after:w-1/2 after:rounded-md after:bg-background after:shadow-sm after:shadow-black/[.04] after:ring-offset-background after:transition-transform after:duration-300 after:[transition-timing-function:cubic-bezier(0.16,1,0.3,1)] has-[:focus-visible]:after:ring-2 has-[:focus-visible]:after:ring-ring has-[:focus-visible]:after:ring-offset-2 data-[state=off]:after:translate-x-0 data-[state=on]:after:translate-x-full"
		data-state={selectedValue}
	>
		<label
			class="relative z-10 inline-flex h-full min-w-8 cursor-pointer items-center justify-center whitespace-nowrap px-4 group-data-[state=on]:text-muted-foreground/70"
		>
			Bill Monthly
			<RadioGroupItem value="off" class="sr-only" />
		</label>
		<label
			class="relative z-10 inline-flex h-full min-w-8 cursor-pointer items-center justify-center whitespace-nowrap px-4 group-data-[state=off]:text-muted-foreground/70"
		>
			<span>
				Bill Yearly <span class="group-data-[state=on]:text-emerald-500">-20%</span>
			</span>
			<RadioGroupItem value="on" class="sr-only" />
		</label>
	</RadioGroup>
</div>
