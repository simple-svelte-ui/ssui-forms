<style>
.borderstyle {
	background-color: transparent !important;
	border-radius: 0 !important;
	border-top: none !important;
	border-left: none !important;
	border-right: none !important;
	border-bottom: 2px solid var(--outline) !important;
}
.no-display {
	display: none;
}
.input-container {
	width: var(--width);
	position: relative;
}
.label {
	font-size: var(--font-size);
	position: absolute;
	left: 10px;
	top: 14px;
	transition: all 0.2s;
	padding: 0 2px;
	z-index: 1;
	color: var(--color);
}
.text-input {
	padding: 0.8rem;
	width: 100%;
	height: 100%;
	border: 1px solid var(--border);
	background: var(--bg);
	border-radius: 5px;
	font-size: var(--font-size);
	line-height: var(--line-height);
	outline: none;
	transition: all 0.3s;
	color: var(--color);
}
.label::before {
	content: '';
	height: 5px;
	position: absolute;
	left: 0;
	top: 0;
	width: 100%;
	z-index: -1;
}
.text-input:focus {
	border: 1px solid var(--outline);
	font-size: var(--font-size);
}
.text-input:focus + .label {
	display: block;
	top: -16px;
	font-size: 14px;
	color: var(--color) !important;
}
.text-input::placeholder {
	font-size: 14px;
	color: var(--color);
	opacity: 0;
	transition: all 0.3s;
}
.text-input:focus::placeholder {
	opacity: 1;
}
</style>

<script>
import { colorscheme, sizechart } from './values';
let outline = true;
let color = 'primary';
let value = '';
let width = '280px';
let label = 'Value';
let required = false;
let placeholder = `Enter the ${label} here...`;
let size = 'normal';
export { color, value, width, label placeholder, size, outline };
</script>

<div
	class="input-container"
	style="--width:{width};--color:{colorscheme[color].color}; --bg:{colorscheme[color]
		.bg};--border:{colorscheme[color].border};--outline:{colorscheme[color].outline};
        --font-size:{sizechart[size].fontSize};--line-height:{sizechart[size]}
        ">
	<input
		type="text"
		placeholder="{placeholder}"
		class="text-input"
		bind:value
		on:blur
		on:change
		on:click
		on:focus
		on:keydown
		on:keypress
		on:keyup
		on:mouseover
		on:mouseenter
		on:mouseleave
		on:paste
		class:borderstyle="{!outline}"
		disabled="{color === 'disabled'}"
		{...$$restProps} />
	<label class:no-display="{value !== ''}" for="{label}" class="label">{label}</label>
</div>
