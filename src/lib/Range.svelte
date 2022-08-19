<style>
.cursor {
	cursor: not-allowed !important;
}
input[type='range'] {
	width: 100%;
	background-color: var(--bg);
	border-radius: 0.5rem;
	appearance: none;
	cursor: pointer;
	height: var(--height);
	margin-bottom: 1.5rem;
}
input[type='range']::-webkit-slider-thumb {
	background-color: var(--color);
}
</style>

<script>
let value;
let id = 'range';
let min;
let max;
let step;
let size = 'normal';
let color = 'disabled';
const sizechart = {
	small: '0.25rem',
	normal: '0.5rem',
	large: '0.75rem'
};
const colorscheme = {
	primary: {
		border: 'rgb(209 213 219)',
		outline: 'rgb(63,131,248)'
	},
	warning: {
		border: 'rgb(253 224 71)',
		outline: 'rgb(234 179 8)'
	},
	error: {
		border: 'rgb(254 242 242)',
		outline: ' rgb(239 68 68)'
	},
	success: {
		border: 'rgb(134 239 172)',
		outline: 'rgb(34 197 94)'
	},
	info: {
		border: 'rgb(147 197 253)',
		outline: 'rgb(59 130 246)'
	},
	secondary: {
		border: ' rgb(216 180 254)',
		outline: 'rgb(168 85 247)'
	},
	disabled: {
		border: 'rgb(229 231 235)',
		outline: '#80787c'
	}
};
export { id, min, max, step };
</script>

<input
	style="--height:{sizechart[size]}; --color:{colorscheme[color].outline};--bg:{colorscheme[color]
		.border}"
	{...$$restProps}
	id="{id}"
	bind:value
	name="{id}"
	type="range"
	min="{min}"
	max="{max}"
	step="{step}"
	on:change
	on:click
	on:keydown
	on:keypress
	on:keyup
	disabled="{color === 'disabled'}"
	class:cursor="{color === 'disabled'}" />
