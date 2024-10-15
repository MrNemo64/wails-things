<script>
	import { ClipboardGetText } from '$lib/wailsjs/runtime/runtime';

	function getWithClipboardGetText() {
		ClipboardGetText().then(console.log).catch(console.error);
	}

	async function getWithJs() {
		if (!navigator.clipboard) throw new Error('No clipboard');
		const items = await navigator.clipboard.read();
		items.forEach((item) => {
			item.presentationStyle;
		});
	}
</script>

<button class="btn btn-neutral" on:click={getWithClipboardGetText}>
	get clipboard with ClipboardGetText
</button>
<button class="btn btn-neutral" on:click={getWithJs}> get clipboard with JS </button>
