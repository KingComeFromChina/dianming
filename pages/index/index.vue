<template>
	<view class="content">
		<view class="conbox">
			<view class="container">
				<image class="cont" src="../../static/bg.jpg"></image>
				<view class="header">
				<view class="header-title">
					<view class="left" @click="start()">
						开始点名 >
					</view>
					<view class="right" @click="stop()">
						停止点名 >
					</view>
				</view>
			</view>
			<view class="main">
				<view class="canvas-container">
					<text class="textStyle">{{name}}</text>
				</view>
			</view>
			</view>
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				timer:null,
				nameArray:[
					"崔万通","闫一航","崔丹妮","谭佳佳","丁鹏耀","崔恒鑫","黄泉皓","黄怡",
					"黄美如","崔豪麟","曹雨博","曹睿睿","黄钰轲","黄铭妍","杨璐铭","黄甜瑞",
					"黄铭扬","黄彦川","陈帅杰","黄一航","周瑞冰","谭淑彤","王宁轩","黄晓飞","谭亚丹"
				],
				name:"准备",
				suijishu:0
			}
		},
		onLoad() {

		},
		methods: {
			start:function(){
				var that = this
				that.timer = setInterval(()=>{
				 
				  
					  that.suijishu = Math.floor(Math.random()*that.nameArray.length)
					   console.log(that.suijishu);
					   that.name = that.nameArray[that.suijishu];
					   console.log(that.name)
				},10)
			},
			
			stop:function(){
				var that = this
				if(this.timer){
					clearInterval(this.timer)
					this.timer = null
					 that.suijishu = Math.floor(Math.random()*that.nameArray.length)
					 console.log(that.suijishu);
					  that.name = that.nameArray[that.suijishu];
					 console.log(that.name)
				}
			}

		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		box-sizing: border-box;
		background-color: #fff;
		
	}
	
	.conbox {
		width: 750upx;
		height: 100vh;
		overflow-x: hidden;
		overflow-y: scroll;
	}

	.container,
	image.cont {
		width: 750upx;
		min-height: 100vh;
		height: auto;
		position: relative;
	}

	image.cont {
		height: 100%;
		position: absolute;
		z-index: 0;
	}

	.header {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		/* height: 246upx; */
		padding-top: 48upx;
		padding-bottom: 40upx;
		box-sizing: border-box;
		position: relative;
		z-index: 3;
	}

	.header-title {
		width: 100%;
		height: 60upx;
		display: flex;
		align-items: center;
		padding: 0 48upx;
		box-sizing: border-box;
		justify-content: space-between;
	}

	.header-title>view {
		padding: 8upx 16upx;
		border: 1px solid #d89720;
		color: #d89720;
		font-size: 28upx;
		border-radius: 26upx;
	}
	.canvas-container {
		margin: 0 auto;
		position: relative;
		width: 600upx;
		height: 600upx;
		background: url(../../static/circle.png) no-repeat;
		background-size: cover;
		border-radius: 50%;
	}
	
	.textStyle{
		color: #DD524D;
		align-items: center;
		
		position: absolute;
		left: 0upx;
		top: 200upx;
		width: 600upx;
		height: 200upx;
		text-align: center;
		font-size: 100upx;
	}
	
</style>
