<script>

	import Transition from './components/Transitions/Transition.svelte';
	import { quintOut } from "svelte/easing";

	export let effects = [
		{
		type: 'slide',
		params: { delay: 250, duration: 1000, easing: quintOut }
		}, {
		type: 'scale',
		params: { delay: 250, duration: 1000, easing: quintOut }
		}, {
		type: 'fly',
		params: { delay: 150, duration: 300, x: 50, y: 0, opacity: 0.3, easing: quintOut }
		}, {
		type: 'fade',
		params: { delay: 250, duration: 100 }
		}, {
		type: 'blur',
		params: { amount: 100 }
		}
	]

</script>

{#each effects as effect}
<p>
  <Transition {effect} />
</p>
{/each}