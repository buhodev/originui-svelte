<script lang="ts">
	import Button from '$lib/components/ui/button.svelte';

	import Plus from '@lucide/svelte/icons/plus';

	let open = $state(false);

	function toggleOpen() {
		open = !open;
	}
</script>

<Button
	class="group rounded-full"
	variant="outline"
	size="icon"
	onclick={toggleOpen}
	aria-expanded={open}
	aria-label={open ? 'Close menu' : 'Open menu'}
>
	<Plus
		class="ease-[cubic-bezier(0.68,-0.6,0.32,1.6)] transition-transform duration-500 group-aria-expanded:rotate-[135deg]"
		size={16}
		stroke-width={2}
		aria-hidden="true"
	/>
</Button>
