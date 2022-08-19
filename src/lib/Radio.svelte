<style>
.container {
	display: flex;
	flex-direction: var(--direction);
	justify-content: space-between;
	padding: 0;
	margin: 0;
}
.items {
	display: inline-flex;
	margin-bottom: var(--space);
}
input[type='radio'] {
	accent-color: var(--color);
	width: auto;
	height: auto;
	margin: 0;
	padding: 0;
	margin-right: 5px;
}
label {
	color: var(--fontcolor);
}
</style>

<script>
export let list = [];
export let group = '';
export let color = 'primary';
export let direction = 'column';
export let space = 'auto';
const colorscheme = {
	primary: { color: '#2476d2', fontColor: 'inherit' },
	warning: { fontColor: 'rgb(234 179 8)', color: 'rgb(253 224 71)' },
	error: { color: '#b70000', fontColor: 'rgb(220,66,10)' },
	success: { color: '#467d32', fontColor: 'rgb(34 197 94)' },
	info: { color: '#17a2b8', fontColor: 'rgb(59 130 246)' },
	secondary: { color: '#6200ee', fontColor: 'rgb(168 85 247)' },
	disabled: { color: '#e0e0e0', fontColor: '#80787c' }
};
</script>

<div
	class="container"
	style="--color:{colorscheme[color].color};--fontcolor:{colorscheme[color]
		.fontColor};--direction:{direction}; --space:{space}">
	{#each list as item}
		<div class="items">
			<input
				type="radio"
				name="radiolist"
				id="{item}"
				value="{item}"
				bind:group
				on:blur
				on:change
				on:click
				on:focus
				on:keydown
				on:keypress
				on:keyup
				on:mouseenter
				on:mouseleave
				on:mouseover
				on:paste
				disabled="{color === 'disabled'}" />
			<label for="radiolist">{item}</label>
		</div>
	{/each}
</div>
