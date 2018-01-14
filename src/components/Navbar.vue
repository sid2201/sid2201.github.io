<template>
	<div class="nav-bar">		
		<div class="left-nav">
			<div class="logo">
				<img src="../assets/logo.png">
			</div>
			<div class="nav-item">
				Boards
				<span class="caret-dropdown">
					<img src="../assets/caret_down.svg">
				</span>
			</div>
			<div class="nav-item">
				Activity
				<div class="activity-badge">2</div>
			</div>
			<div class="nav-item">Teammates</div>
		</div>
		<div class="right-nav">
			<div class="profile-icon">
				<img class="logged-in-user" src="../assets/user_icon_1.png">
				<span class="caret-dropdown">
					<img src="../assets/caret_down.svg">
				</span>
			</div>
		</div>
	</div>
</template>


<style scoped>
	.nav-bar {
		height: 70px;
		background: linear-gradient(to top, #2ea1f8, #1990ea);
		display: flex;
		align-items: center; 
		justify-content: space-between;
		padding: 0 20px; 
		color: #fff;
		position: fixed;
	    width: 100%;
	    top: 0;
	    z-index: 999;
	}

	.nav-bar  .logo {
	    width: 45px;
	    height: 45px;
	    border-radius: 2px;
	    background-color: #1166a5;
	    display: flex;
	    justify-content: center;
	    align-items: center;
	    margin-right: 20px;
	    cursor: pointer;
	}

	.left-nav {
		display: flex;
		font-size: 12px;
		font-weight: 600;
		align-items: center; 
	}

	.right-nav {
		margin-right: 40px;
	}

	.nav-item {
		margin-right: 30px;
		position: relative;
		cursor: pointer;
	}

	.activity-badge {
		width: 18px;
		height: 18px;
		border-radius: 50%;
		background-color: #ff7800;
		display: flex;
		justify-content: center;
		align-items: center;
		font-size: 11px;
		font-weight: 600;
	    position: absolute;
	    right: -12px;
	    top: -13px;
	}

	.caret-dropdown {
		margin-left: 10px;
	}

	.caret-dropdown > img {
		width: 6px;
		height: 6px;
	}

	.profile-icon {
		display: flex;
		align-items: center;
		cursor: pointer;
	}

	.profile-icon > img.logged-in-user {
		width: 40px;
		height: 40px;
		border-radius: 50%;
	}
</style>