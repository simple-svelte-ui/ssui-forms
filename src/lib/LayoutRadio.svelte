<style>
.main {
	display: flex;
	flex-wrap: wrap;
	justify-content: space-between;
	align-items: center;
}
.color {
	background-color: #f5f5f5 !important;
	border: 2px solid rgb(63, 131, 248) !important;
}
.layout {
	margin-top: 10px;
	cursor: pointer;
	min-width: var(--width);
	max-width: var(--width);
}

.layout .layout-content {
	display: -webkit-box;
	display: -ms-flexbox;
	display: flex;
	padding: 30px;
	-webkit-box-sizing: border-box;
	box-sizing: border-box;
	border: 2px solid #e1e2e7;
	border-radius: 10px;
	-webkit-transition: -webkit-box-shadow 0.4s;
	transition: -webkit-box-shadow 0.4s;
	-o-transition: box-shadow 0.4s;
	transition: box-shadow 0.4s;
	transition: box-shadow 0.4s, -webkit-box-shadow 0.4s;
	position: relative;
}
.layout .layout-content img {
	margin-right: 30px;
	height: 72px;
}
.layout .layout-detials span {
	margin-bottom: 10px;
	display: block;
	font-size: 20px;
	line-height: 24px;
	color: #252f42;
}
.layout .layout-detials p {
	font-size: 14px;
	line-height: 18px;
	color: #252f42;
}
.layout .layout-content:hover {
	-webkit-box-shadow: 0px 3px 5px 0px #e8e8e8;
	box-shadow: 0px 3px 5px 0px #e8e8e8;
}
</style>

<script>
export let group = '';
export let width = '500px';
function click(e) {
	group = e;
	console.log(group);
}
export let list = [];
</script>

<div class="main" style="--width:{width}">
	{#each list as l}
		<label for="{l.name}" class="layout" on:click="{() => click(l.name)}">
			<div class="layout-content" class:color="{group === l.name}">
				<img draggable="false" loading="lazy" src="{l.img}" alt="" />
				<div class="layout-detials">
					<span>{l.name}</span>
					<p>
						{l.desc}
					</p>
				</div>
			</div>
		</label>
	{/each}
</div>
