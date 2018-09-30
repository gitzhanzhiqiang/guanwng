<template>
	<div class="app-container calendar-list-container servicePage">
		<div class="banner">
			<img :src="img1">
			<div class="btm" @click="go_url()" style="cursor:pointer ;"> APPLY NOW
			</div>
			<p>INVESTMENT MANAGEMENT<br /> In the sunfin ,quality <br /> investment products are within reach.</p>
		</div>
		<div class="Partner" :style="beijin">
			<div class="high">
				<ul>
					<li v-for="itm in higha" v-on:mouseenter="cleanTime(itm)" v-on:mouseleave="setTime(itm)">
						<img :class="{'imga1': itm.stat}" src="~@res/imgd/huand1.png" />
						<img :class="{'imga2': itm.stat}" src="~@res/imgd/huand2.png" />
						<p v-html="itm.wenzi"></p>
					</li>
					
				</ul>
			</div>
			<div class="titd">
				<h1>OUR PODUCT PRESENTATION</h1>
			</div>
			<div class="product">
				<ul>
					<li>
						<i></i>
						<img class="shuzi" src="~@res/imgd/one1.png"/>
						<div class="wenzi">
							<h3>BOND</h3>
							<p>Selected bonds issued by outstanding global companies and government are to provide customers with more moderate earnings.</p>
							<a>LEARN MORE</a>
						</div>	
						<img class="imgj" src="~@res/imgd/shouji.png"/>
					</li>
					<li>
						<i></i>
						<img class="imgj" src="~@res/imgd/shouji.png"/>
						
						<div class="wenzi">
							<h3>REAL ESTATE</h3>
							<p>ooking for real estate projects with great potential for value growth around the world and taking advantage of the investment opportunities in the first-hand market.</p>
							<a>LEARN MORE</a>
						</div>	
						<img class="shuzi" src="~@res/imgd/one2.png"/>
					</li>
					<li>
						<i></i>
						<img class="shuzi" src="~@res/imgd/one3.png"/>
						<div class="wenzi">
							<h3>FUNDS</h3>
							<p>Work with world-class fund companies and asset management teams to help clients diversify their investments in different assets, markets and currencies.</p>
							<a>LEARN MORE</a>
						</div>	
						<img class="imgj" src="~@res/imgd/shouji.png"/>
					</li>
				</ul>
			</div>
		</div>
	</div>
</template>
<script>
	import ajax from '@utils/config';
	import { WOW } from 'wowjs';
	export default {
		data() {
			var beijin = require("@res/imgd/beijin1.png");
			return {
				titia: 'Blue star grade:',
				img1: require("@res/imgd/bannercc.png"),
				xing: require("@res/imgs/xinga.png"),
				count: '1',
				beijin: {
					backgroundImage: "url(" + beijin + ")",
				},
				higha:[
					{
						img1:require("@res/imgd/huand1.png"),
						img2:require("@res/imgd/huand2.png"),
						stat:true,
						id:1,
						wenzi:'Integrating<br /> global investment<br />  resources',
					},
					{
						img1:require("@res/imgd/huand1.png"),
						img2:require("@res/imgd/huand2.png"),
						stat:false,
						id:2,
						wenzi:'High level <br />professional team',
					},
					{
						img1:require("@res/imgd/huand1.png"),
						img2:require("@res/imgd/huand2.png"),
						stat:false,
						id:3,
						wenzi:'Tailor-made inves<br />tment and financial <br />management plans',
					}
				],
			}
		},
		computed: {},
		created() {
			//this.setTime()
			this.fanding()
		},
		mounted() {
			new WOW().init()
		},
		methods: {
			go_url() {
				this.$store.dispatch('NAVSET', {
					nav: true
				});
				this.$router.push({
					path: '/sunfin/contactUs'
				})
			},
			fanding() {
				window.scrollTo(0, 0);
			},
			setTime(itm) {
				this.higha.map((item) => {
					if(item.id == 1){
						item.stat = true
					} else {
						item.stat = false
					}
				})
			},
			cleanTime(itm) {
				this.higha.map((item) => {
					if(item.id == itm.id) {
						item.stat = true
					} else {
						item.stat = false
					}
				})
			}
		},
		filters: {}
	}
</script>
<style lang="less" scoped>
.titd h1{
	padding: 100px 0 60px 0px;
}
	.banner {
		position: relative;
	}
	
	.banner .btm {
		width: 260px;
		height: 60px;
		border: 1px solid rgba(255, 255, 255, 1);
		border-radius: 30px;
		text-align: center;
		line-height: 60px;
		font-size: 14px;
		font-family: MicrosoftYaHei;
		font-weight: 400;
		color: white;
		position: absolute;
		left: 399px;
		bottom: 100px;
	}
	.banner img {
		width: 100%;
		height: 100%;
	}
	
	.banner P {
		font-size:48px;
		font-family:MyriadPro-Bold;
		font-weight: bold;
		color:rgba(242,242,245,1);
		line-height:66px;
		position: absolute;
		left: 399px;
		bottom: 225px;
	}
	
	.Partner {
		width: 100%;
		height: 1526px;
		background-size: 100% 100%;
	}
	.high {
		width: 1200px;
		overflow: hidden;
		margin: 0 auto;
	}
	.high ul li img {
		filter: drop-shadow(10px 8px 0px #b9becb) drop-shadow(0px 0px 0px #b9becb) drop-shadow(0px 0px 0px #b9becb);
		-webkit-filter: drop-shadow(10px 8px 0px #b9becb) drop-shadow(0px 0px 0px #b9becb) drop-shadow(0px 0px 0px #b9becb);
	}
	.high ul {
		width: 100%;
		overflow: hidden;
		margin-top: 100px;
	}
	.high ul li {
		width: 317px;
		height: 282px;
		position: relative;
		float: left;
		margin-right: 115px;
		cursor: pointer;
	}
	.high ul li:last-child{
		margin-right: 0px;
	}
	.high ul li img{
		width: 100%;
		height: 273px;
	}
	.high ul li img{
		position: absolute;
	}
	.high ul li p{
		position: absolute;
		width:190px;
		height: 85px;
		font-size:20px;
		font-family:MyriadPro-Regular;
		font-weight:400;
		color:rgba(255,255,255,1);
		top: 95px;
		left: 80px;
		text-align: center;
	}
	.high ul li img.imga1{
		top: -284px;
	}
	.high ul li .imga1{
		animation:myfirst 0.5s infinite;
		animation-iteration-count:1;
	    animation-fill-mode:forwards;
	}
	@keyframes myfirst
		{
		0%  {top:-284px;}
		
		100% {top:0px;}
		}
		
		.high ul li .imga2{
		animation:myfirsta 0.5s infinite;
		animation-iteration-count:1;
	    animation-fill-mode:forwards;
	}
	@keyframes myfirsta
		{
		0%  {top:0px;}
		
		100% {top:-284px;}
		}
		.product{
			width: 1200px;
			overflow: hidden;
			margin: 0 auto;
		}
		.product ul li{
			width:1200px;
			height:237px;
			background:rgba(255,255,255,1);
			border-radius:8px;
			box-shadow:0px 22px 40px rgba(16,34,83,0.05);
			position: relative;
			margin-bottom: 30px;
			cursor: pointer;
		}
		.product ul li:nth-child(odd) i{
			width:2px;
			height:228px;
			background:rgba(58,98,210,1);
			display: block;
			position: absolute;
			left: 0px;
			top: -230px;
			z-index: -1;
		}
		.product ul li:nth-child(even) i{
			width:1px;
			height:228px;
			background:rgba(58,98,210,1);
			display: block;
			position: absolute;
			right: 0px;
			top: -230px;
			z-index: -1;
		}
		.product ul li:hover i{
			animation:myfirstb 0.5s infinite;
			animation-iteration-count:1;
		    animation-fill-mode:forwards;
		    z-index: 0;
		}
		@keyframes myfirstb
		{
		0%  {top:-230px;}
		
		100% {top:5px;}
		}
		/*奇数*/
		.product ul li:nth-child(odd) img.shuzi{
			width: 170px;
			height: 100%;
			display: block;
			float: left;
			margin-left: 20px;
		}
		.product ul li:nth-child(odd) img.imgj{
			width:310px;
			height:170px;
			float: right;
			box-shadow: 7px 7px 20px #cbcdd4;
			margin-right: 42px;
			margin-top: 28px;
		}
		.product ul li:nth-child(odd) .wenzi{
			width: 600px;
			height: 100%;
			float: left;	
			position: relative;	
		}
		.product ul li:nth-child(odd) .wenzi h3{
			font-size:20px;
			font-family:SenticoSansDT-Light;
			font-weight:bold;
			color:rgba(0,0,0,1);
			padding: 30px 0px 20px 0px;
		}
		.product ul li:nth-child(odd) .wenzi p{
			font-size:16px;
			line-height: 25px;
			font-family:SenticoSansDT-Light;
			font-weight:normal;
			color:#444444;
			text-overflow: ellipsis;
		    display: -webkit-box;
		    -webkit-box-orient: vertical;
		    -webkit-line-clamp: 3;
		    overflow: hidden;
		}
		.product ul li .wenzi a{
			position: absolute;
			bottom: 40px;
			right: 0px;
			font-size:14px;
			font-family:MyriadPro-Regular;
			font-weight:400;
			color:rgba(102,110,209,1);
			cursor: pointer;
		}
		/*偶数*/
		.product ul li:nth-child(even) img.shuzi{
			width: 170px;
			height: 100%;
			display: block;
			float: right;
			margin-right:10px;
		}
		.product ul li:nth-child(even) img.imgj{
			width:310px;
			height:170px;
			float: left;
			box-shadow: 7px 7px 20px #cbcdd4;
			margin-left: 42px;
			margin-top: 28px;
			margin-right: 50px;
		}
		.product ul li:nth-child(even) .wenzi{
			width: 600px;
			height: 100%;
			float: left;	
			position: relative;	
		}
		.product ul li:nth-child(even) .wenzi h3{
			font-size:20px;
			font-family:SenticoSansDT-Light;
			font-weight:bold;
			color:rgba(0,0,0,1);
			padding: 30px 0px 20px 0px;
		}
		.product ul li:nth-child(even) .wenzi p{
			font-size:16px;
			line-height: 25px;
			font-family:SenticoSansDT-Light;
			font-weight:normal;
			color:#444444;
			text-overflow: ellipsis;
		    display: -webkit-box;
		    -webkit-box-orient: vertical;
		    -webkit-line-clamp: 3;
		    overflow: hidden;
		}
</style>