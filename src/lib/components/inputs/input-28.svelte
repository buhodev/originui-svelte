<script lang="ts">
	import Label from '$lib/components/ui/label.svelte';

	import Minus from '@lucide/svelte/icons/minus';
	import Plus from '@lucide/svelte/icons/plus';

	let value = $state(2048);
	const minValue = 0;

	function increment() {
		value++;
	}

	function decrement() {
		if (value > minValue) {
			value--;
		}
	}

	function handleInput(event: Event) {
		const input = event.target as HTMLInputElement;
		const newValue = Number.parseInt(input.value, 10);
		if (!Number.isNaN(newValue) && newValue >= minValue) {
			value = newValue;
		} else {
			input.value = value.toString();
		}
	}

	const uid = $props.id();
</script>

<div class="space-y-2">
	<Label for={uid} class="text-sm font-medium text-foreground">
		Number input with plus/minus buttons
	</Label>
	<div
		class="relative inline-flex h-9 w-full items-center overflow-hidden whitespace-nowrap rounded-lg border border-input text-sm shadow-sm shadow-black/[.04] ring-offset-background transition-shadow focus-within:border-ring focus-within:outline-none focus-within:ring-2 focus-within:ring-ring/30 focus-within:ring-offset-2"
	>
		<button
			id="decrement-button"
			onclick={decrement}
			class="-ms-px flex aspect-square h-[inherit] items-center justify-center rounded-s-lg border border-input bg-background text-sm text-muted-foreground/80 ring-offset-background transition-shadow hover:bg-accent hover:text-foreground disabled:pointer-events-none disabled:cursor-not-allowed disabled:opacity-50"
			aria-label="Decrease value"
			aria-labelledby="decrement-button {uid}"
			aria-controls={uid}
			disabled={value <= minValue}
		>
			<Minus size={16} stroke-width={2} aria-hidden="true" />
		</button>
		<input
			id={uid}
			type="text"
			bind:value
			oninput={handleInput}
			aria-labelledby={uid}
			autocomplete="off"
			inputmode="numeric"
			autocorrect="off"
			aria-roledescription="Number input"
			spellcheck="false"
			min={minValue}
			class="w-full grow bg-background px-3 py-2 text-center tabular-nums text-foreground focus:outline-none"
		/>
		<button
			id="increment-button"
			onclick={increment}
			class="-me-px flex aspect-square h-[inherit] items-center justify-center rounded-e-lg border border-input bg-background text-sm text-muted-foreground/80 ring-offset-background transition-shadow hover:bg-accent hover:text-foreground disabled:pointer-events-none disabled:cursor-not-allowed disabled:opacity-50"
			aria-label="Increase value"
			aria-labelledby="increment-button {uid}"
			aria-controls={uid}
		>
			<Plus size={16} stroke-width={2} aria-hidden="true" />
		</button>
	</div>
</div>
