<template>
	<div class="card" :style="cardColor">
		<div v-if="this.item.thumbnail" class="card-thumb">
			<img :src="require(`@/assets/thumb_${this.item.thumbnail}.png`)">
		</div>
		<div class="card-title">
			{{ this.item.title }}
		</div>
		<div v-if="this.item.comments || this.item.checks || this.item.users || this.item.time" class="card-footer">
			<div class="left-section">
				<div v-if="this.item.time" class="time">
					<div class="icon">
						<img src="../assets/clock.svg">
					</div>
					<div class="text">
						{{ this.item.time }}
					</div>
				</div>
				<div v-if="this.item.comments" class="comments">
					<img src="../assets/comments.svg">
					<span class="comment-count">{{ this.item.comments.count }}</span>
				</div>
				<div v-if="this.item.checks" class="check">
					<img src="../assets/checkbox.svg">
					<span class="check-count">{{ this.item.checks.count[0] }}/{{ this.item.checks.count[1] }}</span>
				</div>
			</div>			
			<div class="right-section">
				<div v-if="this.item.users" class="users">
					<template v-for="(user, index) in this.item.users">
						<img :class="user_position(index)" :src="require(`@/assets/user_icon_${user}.png`)"/>
					</template>					
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		props: ["item"],

		computed: {
			cardColor() {
				return "border-left: 3px solid "+this.item.card_color;
			}
		},

		methods: {
			user_position: function(index) {
				return "user-icon user-" + (index+1);
			}
		}
	}	
</script>

<style scoped>
	.card {
		margin-top: 10px;
		padding: 10px;
		border-radius: 3px;
		border: 0.5px solid #e6eaee;
	}

	.card-thumb {
		margin: -12px -10px 0 -10px;
	}

	.card-thumb > img {
	    width: 100%;
	    border-top-left-radius: 5px;
	    border-top-right-radius: 5px;
	}

	.card-title {
		font-size: 12px;
		color: #354052;
		font-weight: 600;
		line-height: 1.36;
	}

	.card-footer {
		display: flex;
		justify-content: space-between;
		margin-top: 10px;
	}

	.left-section {
		display: flex;
		align-items: center;
	}

	.comments > img {
		width: 16px;
		position: relative;
		top: 5px;
	}

	.check {
		margin-left: 15px;
	}

	.check > img {
		width: 12px;
		position: relative;
		top: 2px;
	}

	.comment-count, .check-count {
		color: #7f8fa4;
		font-size: 11px;
		font-weight: 600;
		position: relative;
	    left: 2px;
	}

	.check-count {
		letter-spacing: 1px;
	}

	.users {
		position: relative;
		height: 35px;
		min-width: 35px;
	}

	.user-icon {
		width: 35px;
		height: 35px;
		border-radius: 50%;
		position: absolute;
		border: 0.5px solid #fff;
	}

	.user-1 {
		z-index: 2;
	}

	.user-2 {
		right: 25px;
		z-index: 1;
	}

	.time {
		width: 65px;
		height: 20px;
	    display: flex;
	    justify-content: space-around;
	    align-items: center;
	    background-color: #ff4b64;
	    border-radius: 5px;
	    color: #fff;
	    font-size: 12px;
	    font-weight: 600;
	}

	.time > .icon > img {
		width: 12px;
		height: 12px;
		position: relative;
	    top: 1px;
	    left: 1px;
	}

	.time > .text {
	    position: relative;
	    right: 3px;
	    bottom: 1px;
	}
</style>