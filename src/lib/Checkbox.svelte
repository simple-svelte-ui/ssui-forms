<style>
.content {
	display: inline-flex;
}
input[type='checkbox'] {
	accent-color: var(--color);
	width: auto;
	height: auto;
	margin: 0;
	padding: 0;
	margin-right: 5px;
}
input[type='checkbox']:focus {
	border: 1px solid var(--color);
}
input[type='checkbox']:checked {
	border-color: transparent;
}
label {
	color: var(--fontColor);
}
</style>

<script>
let checked = undefined;
let color = 'primary';
const colorscheme = {
	primary: { color: '#2476d2', fontColor: 'inherit' },
	warning: { fontColor: 'rgb(234 179 8)', color: 'rgb(253 224 71)' },
	error: { color: '#b70000', fontColor: 'rgb(220,66,10)' },
	success: { color: '#467d32', fontColor: 'rgb(34 197 94)' },
	info: { color: '#17a2b8', fontColor: 'rgb(59 130 246)' },
	secondary: { color: '#6200ee', fontColor: 'rgb(168 85 247)' },
	disabled: { color: '#e0e0e0', fontColor: '#80787c' }
};
export { checked, color };
</script>

<div
	class="content"
	style="--color:{colorscheme[color].color};  --fontColor:{colorscheme[color].fontColor}; --">
	<input
		type="checkbox"
		bind:checked
		on:keyup
		on:keydown
		on:keypress
		on:focus
		on:blur
		on:click
		on:mouseover
		on:mouseenter
		on:mouseleave
		on:paste
		disabled="{color === 'disabled'}"
		{...$$restProps} />
	<label for=""><slot /></label>
</div>
