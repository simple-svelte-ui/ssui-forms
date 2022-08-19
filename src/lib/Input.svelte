<style>
.borderstyle {
	background-color: transparent !important;
	outline: none !important;
	border-top: none !important;
	border-left: none !important;
	border-right: none !important;
	border-bottom: 2px solid var(--border) !important;
}
.disablecursor {
	cursor: not-allowed !important;
}
.inputg {
	position: relative;
}
.inputg input {
	padding-left: var(--icon);
}
input:focus {
	outline-color: var(--outline) !important;
}
.inputg i {
	position: absolute;
	top: var(--imgtop);
	left: 0.4em;
	color: var(--icon);
	font-size: 1.5em;
	color: var(--imgcolor);
	transition: 0.3s;
}
input[type='file']::-webkit-file-upload-button {
	display: none;
}
input[type='file']::-file-selector-button {
	display: none;
}
</style>

<script>
import { colorscheme, sizechart } from './values';
let value = '';
let width = '280px';
let color = 'primary';
let placeholder = 'Enter here...';
let icon = null;
let size = 'normal';
let required = false;
let outline = true;

export { value, width, color, placeholder, icon, size, outline };
</script>

<div
	class="inputg"
	style="--imgcolor:{colorscheme[color].color};--imgtop:{size === 'large' ? '0.4em' : '15%'};">
	<input
		style="width:{width};background-color:{colorscheme[color].bg};color:{colorscheme[color]
			.color};border: 1px solid {colorscheme[color].border}; 
            font-size:{sizechart[size].fontSize};
            line-height:{sizechart[size].lineheight};
            --border:{color === 'disabled' ? colorscheme[color].color : colorscheme[color].outline};
            --outline:{colorscheme[color].outline};
            --icon:{icon == undefined ? '10px' : '40px'};
            "
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
		placeholder="{placeholder}"
		disabled="{color === 'disabled'}"
		class:disablecursor="{color === 'disabled'}"
		class:borderstyle="{!outline}"
		required="{required}"
		{...$$restProps} />
	<i class="{icon}" aria-hidden="true"></i>
</div>
