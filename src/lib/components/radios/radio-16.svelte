<script lang="ts">
	import { RadioGroup, RadioGroupItem } from '$lib/components/ui/radio-group/index.js';

	const items = [
		{ icon: '😠', id: 'radio-16-r1', label: 'Angry', value: 'r1' },
		{ icon: '🙁', id: 'radio-16-r2', label: 'Sad', value: 'r2' },
		{ icon: '😐', id: 'radio-16-r3', label: 'Neutral', value: 'r3' },
		{ icon: '🙂', id: 'radio-16-r4', label: 'Happy', value: 'r4' },
		{ icon: '😀', id: 'radio-16-r5', label: 'Laughing', value: 'r5' }
	];

	let selectedValue = $state('r3');
</script>

<fieldset class="space-y-4">
	<legend class="text-sm font-medium leading-none text-foreground">How did it go?</legend>
	<RadioGroup class="flex gap-1.5" bind:value={selectedValue}>
		{#each items as item (item.id)}
			<label
				class="relative flex size-9 cursor-pointer flex-col items-center justify-center rounded-full border border-input text-center text-xl shadow-sm shadow-black/[.04] ring-offset-background transition-colors has-[[data-disabled]]:cursor-not-allowed has-[[data-state=checked]]:border-ring has-[[data-state=checked]]:bg-accent has-[[data-disabled]]:opacity-50 has-[:focus-visible]:ring-2 has-[:focus-visible]:ring-ring/70 has-[:focus-visible]:ring-offset-2"
			>
				<RadioGroupItem
					id={item.id}
					value={item.value}
					class="sr-only after:absolute after:inset-0"
				/>
				{item.icon}
			</label>
		{/each}
	</RadioGroup>
</fieldset>
