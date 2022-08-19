<style>
.toggle-btn {
	position: relative;
	width: var(--frist);
	height: var(--sec);
	background: var(--tbg);
	border-radius: 30px;
	padding: 5px;
	transition: all var(--duration) ease-in-out;
}

.inner-circle {
	position: absolute;
	width: var(--sec);
	height: var(--sec);
	background: var(--col);
	border-radius: 50%;
	transition: all var(--duration) ease-in-out;
}
.toggle-btn.active {
	background: var(--atb);
}
.toggle-btn.active > .inner-circle {
	margin-left: var(--sec);
}
</style>

<script>
import { createEventDispatcher } from 'svelte';
import { colorscheme, sizechart } from './values';
const dispatch = createEventDispatcher();
export let checked = false;
export let size = 'normal';
export let color = 'primary';
export let duration = '100ms';
function onClick(e) {
	if (color !== 'disabled') {
		checked = !checked;
	}
	dispatch('click', e);
}
</script>

<div
	class="toggle-btn"
	on:click="{onClick}"
	class:active="{checked}"
	style="--frist:{sizechart[size].a};--sec:{sizechart[size].b};--tbg:{colorscheme[color]
		.border};--atb:{colorscheme[color].outline};--col:{colorscheme[color]
		.bg}; --duration:{duration};">
	<div class="inner-circle"></div>
</div>
