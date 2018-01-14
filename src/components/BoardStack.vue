<template>
	<div class="board-stack">
		<div class="board-header" :style="{borderColor: this.item.stack_color}">
			<div class="board-title">
				{{ this.item.name }}
				<span class="card-count">{{ this.item.card_count }}</span>
			</div>
			<div class="board-options">
				<img src="../assets/three_dots.svg">
			</div>
		</div>
		<div class="board-body">
			<template v-for="card in this.item.cards">
				<card :item="card"></card>
			</template>
		</div>
		<div @click="addNewCard()" class="add-card-icon">
			<img src="../assets/add_icon_white.svg">
		</div>
	</div>			
</template>

<script>
	import Card from '@/components/Card'

	export default {
		components: {
			'card': Card
		},

		props: ["item"],

		methods: {
			addNewCard: function() {
				Event.$emit('add-new-card-to-board', this.item.id);
			}
		}
	}
</script>

<style scoped>
	.board-stack {
		width: 270px;
		height: 100%;
		position: relative;
		background-color: #f7f9fb;
		flex: none;
	}
	.board-title {
		font-size: 13px;
		font-weight: 600;
		color: #354052;
	}
	.board-stack {
		margin: 0 15px;
	}

	.board-header {
		display: flex;
		justify-content: space-between;
		padding: 5px 0;
		background-color: #eff3f6;
		border-bottom: 3px solid transparent;
	}

	.board-body {
		padding: 0 10px 10px 10px; 
	}

	.card-count {
		color: #7f8fa4;
		margin-left: 2px;
	}

	.board-options {
		cursor: pointer;
	}

	.board-options > img {
		width: 18px;
	}

	.add-card-icon {
		position: absolute;
		left: 10px;
		bottom: -13px; 
		cursor: pointer;
		display: flex;
		justify-content: center;
		align-items: center;
		width: 30px;
		height: 30px;
		border-radius: 50%;
		background-image: linear-gradient(to top, #1991eb, #2da1f8);
	}

	.add-card-icon > img {
		width: 10px;
		height: 10px;
		-webkit-transition: -webkit-transform 0.35s;
		-moz-transition: -moz-transform 0.35s;
		transition: transform 0.35s;
	}

	.add-card-icon:hover > img {
		-webkit-transform: scale(1.2, 1.2);
		-moz-transform: scale(1.2, 1.2);
		transform: scale(1.2, 1.2);
	}
</style>