<script lang="ts">
	import '../app.css';
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();

	let activeSection = '';

	function scrollToSection(sectionId: string) {
		const el = document.getElementById(sectionId);
		if (el) {
			el.scrollIntoView({ behavior: 'smooth' });
			activeSection = sectionId;
		}
	}
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>


<div class="top-0 h-16 z-50 items-right flex justify-end gap-8 p-4 pr-10 fixed w-full  ">
	<button on:click={() => scrollToSection('about')} class="text-xl hover:text-orange-600 inconsolata">About</button>
	<button on:click={() => scrollToSection('works')} class="text-xl hover:text-orange-600 inconsolata">Works</button>
</div>

<div class="bottom-0 h-12 z-50 items-left flex justify-start gap-8 p-4 pr-10 fixed w-full  ">
	<a class="text-xs text-gray-400 hover:text-orange-700" href="https://github.com/nopan-studio">@nopan-studio</a>
</div>
{@render children?.()}
