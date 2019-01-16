<template>
	<div>
		<p>welcome to my demo!</p>
		<!--iview  layout布局-->
		<div class="layout" :class="{'layout-hide-text': spanLeft < 5}">
			<Row type="flex">   
				<i-col :span="spanLeft" class="layout-menu-left">
					<i-menu active-name="1-2" theme="dark" width="auto" :open-names="['1']">
						<div class="layout-logo-left"></div>
						<Submenu name="1">
							<template slot="title">
								<Icon type="ios-navigate" :size="iconSize"></Icon>
								<span class="layout-text">导航一</span>
							</template> 
							<Menu-item name="1-1">选项 1</Menu-item>
							<Menu-item name="1-2">选项 2</Menu-item>
							<Menu-item name="1-3">选项 3</Menu-item>
						</Submenu>
						<Submenu name="2">
							<template slot="title">
								<Icon type="ios-keypad" :size="iconSize"></Icon>
								<span class="layout-text">导航二</span>
							</template>
							<Menu-item name="2-1">选项 1</Menu-item>
							<Menu-item name="2-2">选项 2</Menu-item>
						</Submenu>
						<Submenu name="3"> 
							<template slot="title">
								<Icon type="ios-analytics" :size="iconSize"></Icon>
								<span class="layout-text">导航三</span>
							</template>
							<Menu-item name="3-1">选项 1</Menu-item>
							<Menu-item name="3-2">选项 2</Menu-item>
							<Menu-item name="3-3">选项 3</Menu-item>
						</Submenu>
						<Submenu name="4">
							<template slot="title">
								<Icon type="ios-paper" :size="iconSize"></Icon>
								<span class="layout-text">导航四</span>
							</template>
							<Menu-item name="4-1">选项 1</Menu-item>
							<Menu-item name="4-2">选项 2</Menu-item>
						</Submenu>
						<Submenu name="5">
							<template slot="title">
								<Icon type="ios-search" :size="iconSize"></Icon>
								<span class="layout-text">导航五</span>
							</template>
							<Menu-item name="5-1">选项 1</Menu-item>
							<Menu-item name="5-2">选项 2</Menu-item>
						</Submenu>
						<Submenu name="6">
							<template slot="title">
								<Icon type="ios-settings" :size="iconSize"></Icon>
								<span class="layout-text">导航六</span>
							</template>
							<Menu-item name="6-1">选项 1</Menu-item>
						</Submenu>
					</i-menu>

				</i-col>
				<i-col :span="spanRight">
					<div class="layout-header">
						<i-button type="text" @click="toggleClick">
							<Icon type="navicon" size="32"></Icon>
						</i-button>
					</div>
					<div class="layout-breadcrumb">
						<Breadcrumb>
							<Breadcrumb-item href="#">首页</Breadcrumb-item>
							<Breadcrumb-item href="#">应用中心</Breadcrumb-item>
							<Breadcrumb-item>子应用</Breadcrumb-item>
						</Breadcrumb>
					</div>
					<div class="layout-content">
						<div class="layout-content-main" :style="contentStyle">content</div>
						<!--iview分页-->
						<Page :total="1000" show-elevator />
					</div>
					<div class="layout-copy">
						2019 &copy; zmy
					</div>
				</i-col>
			</Row>
		</div>

	</div>
</template>
<script>
	export default {
		data() {
			return {
				spanLeft: 5,
				spanRight: 19,
				theme1: 'dark'

			}
		},
		computed: {
			iconSize: function() {
				return this.spanLeft === 5 ? 14 : 24;
			},
			contentStyle: function() {
				var innerHeight = window.innerHeight;
				var contentHeight = innerHeight - 50 - 110;
				return "min-height: " + contentHeight + "px";
			}
		},
		methods: {
			toggleClick: function() {
				if(this.spanLeft === 5) {
					this.spanLeft = 2;
					this.spanRight = 22;
				} else {
					this.spanLeft = 5;
					this.spanRight = 19;
				}
			}
		}

	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
	p:first-child {
		font-family: "Hiragino Sans GB";
		font-size: 22px;
	}
	
	.layout {
		border: 1px solid #d7dde4;
		background: #f5f7f9;
		position: relative;
		border-radius: 4px;
		overflow: hidden;
	}
	
	.layout-logo {
		width: 100px;
		height: 30px;
		background: #5b6270;
		border-radius: 3px;
		float: left;
		position: relative;
		top: 15px;
		left: 20px;
	}
	
	.layout-nav {
		width: 420px;
		margin: 0 auto;
		margin-right: 20px;
	}
	/**/
	
	.layout {
		*border: 1px solid #d7dde4;
		background: #f5f7f9;
		position: relative;
		border-radius: 4px;
		overflow: hidden;
	}
	
	.layout-breadcrumb {
		padding: 10px 15px 0;
	}
	
	.layout-content {
		min-height: 200px;
		margin: 15px;
		overflow: hidden;
		background: #fff;
		border-radius: 4px;
	}
	
	.layout-content-main {
		padding: 10px;
	}
	
	.layout-copy {
		text-align: center;
		padding: 10px 0 20px;
		color: #9ea7b4;
	}
	
	.layout-menu-left {
		background: #464c5b;
	}
	
	.layout-header {
		height: 50px;
		background: #fff;
		box-shadow: 0 1px 1px rgba(0, 0, 0, .1);
	}
	
	.layout-logo-left {
		width: 90%;
		height: 30px;
		background: #5b6270;
		border-radius: 3px;
		margin: 15px auto;
	}
	
	.layout-ceiling-main a {
		color: #9ba7b5;
	}
	
	.layout-hide-text .layout-text {
		display: none;
	}
	
	.ivu-col {
		transition: width .2s ease-in-out;
	}
</style>