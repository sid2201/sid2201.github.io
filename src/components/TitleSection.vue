<template>
	<div class="title-section">
		<div class="left-section">
			<div class="page-title">Design Backlog</div>
			<div class="pipe-separator">|</div>
			<div class="page-subtitle">Dashboard Design Team</div>
		</div>
		<div class="right-section">
			<div class="search-box">
				<input type="text" name="search" placeholder="search">
				<img src="../assets/search_icon.svg">
			</div>
			<button class="add-btn-primary">
				<img class="add-icon-primary" src="../assets/add_icon_primary.svg">
				New Card
			</button>
		</div>
	</div>
</template>

<style scoped>
.title-section {
	padding: 15px 20px; 
	display: flex;
	align-items: center;
	justify-content: space-between;
	background-color: #fff;
}

.left-section, .right-section {
	display: flex;
	align-items: center;
}

.page-title {
	font-weight: 600;
	color: #354052;
	font-size: 14px;
}

.page-subtitle {
	font-size: 12px;
	color: #7f8fa4;
}

.pipe-separator {
	color: #dfe3e9;
	margin: 0 10px;
}

.search-box {
	position: relative;
}

.search-box > input {
	border-radius: 3px;
	border: solid 0.5px #dfe3e9;
	height: 35px;
	width: 220px;
	padding: 0 10px;
	padding-right: 30px;
}

.search-box > img {
	width: 15px;
    height: 15px;
    position: absolute;
    right: 10px;
    bottom: 11px;
}

.add-btn-primary {
	height: 35px;
	background-color: initial;
	border-radius: 2px;
	font-size: 12px;
	font-weight: 600;
	cursor: pointer;
	color: #fff; 
  	background-image: linear-gradient(to top, #1991eb, #2da1f8);
  	border: solid 0.5px #1585d8;
    padding: 0 22px 0 27px;
    margin-left: 10px;
}

.add-icon-primary {
	width: 10px;
	height: 10px;
	position: relative;
	right: 11px;
}
</style>