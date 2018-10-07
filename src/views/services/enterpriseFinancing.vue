<template>
	<div class="app-container calendar-list-container ggg_user">
		 <div class="banner">
			<img :src="img1">
			<div class="btm" @click="go_url" style="cursor:pointer ;">
				APPLY NOW
			</div>
			<p>INSUEANCE SERVICE<br />Working with several leading financial <br />
and insurance companies in the world.</p>
		</div>
		<div class="con">
			<div class="tita">
				<p>We are working closely with global leading private banks, insurance companies, fund investment linking insurance platforms, trust companies and<br /> other financial institutions in partnership with insurance companies.<br />
To capture investing hotspots worldwide and realize the target of robust value-added investment, we dedicated to create an international<br /> vision of investment for global customers and provide diversified financial services through professional and meticulous services.</p>
			</div>
			<div class="type">
				<h2>TYPE OF INSURANCE</h2>
				<div class="type_st" :style="beicaddd">
					<ul>
						<li :style="litu">
							<img src="~@res/imgd/renwu1.png"/>
							<p>OWERSEAS STUDENT INSURANCE</p>
						</li>
						<li :style="litu">
							<img src="~@res/imgd/renwu2.png"/>
							<p>OWERSEAS STUDENT INSURANCE</p>
						</li>
						<li :style="litu">
							<img src="~@res/imgd/renwu3.png"/>
							<p>OWERSEAS STUDENT INSURANCE</p>
						</li>
					</ul>
				</div>
			</div>
		</div>
	</div>
</template>
<script>
	import ajax from '@utils/config';
	import {WOW} from 'wowjs';
	export default {
		data() {
			var beicaddd = require("@res/imgd/beicaddd.png");
			var litu = require("@res/imgd/litu.png");
			return {
				img1: require("@res/imgd/bannercc.png"),
				beicaddd:{
					backgroundImage: "url(" + beicaddd + ")",
				},
				litu:{
					backgroundImage: "url(" + litu + ")",
				},
			}
		},
		computed: {

		},
		created() {this.fanding()},
		mounted() {
			new WOW().init() 
		},
		methods: {
			go_url() {
				this.$store.dispatch('NAVSET', { nav: true });
				this.$router.push({
					path: '/sunfin/contactUs'
				})
			},
			fanding(){
				window.scrollTo(0,0);
			},
		},
		filters: {}
	}
</script>
<style lang="less" scoped>
.banner{
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
	overflow: hidden;
}
.Partner P{
	width:918px;
	font-size:14px;
	font-family:ArialMT;
	font-weight:400;
	color:#808080;
	line-height: 25px;
	margin: 0 auto;
	margin-bottom: 43px;
}
.Partner img{
	width: 100%;
	height: 280px;
	margin-bottom: 58px;
}
.tita{
	width: 100%;
	overflow: hidden;
}
.tita p{
	text-align: center;
	font-size:16px;
	font-family:SenticoSansDT-Light;
	font-weight:normal;
	color:#333333;
	line-height: 25px;
	padding: 80px 0px 0px 0px;
}
.type {
	width: 100%;
	overflow: hidden;
	position: relative;
	padding: 99px 0px 0px 0px;
}
.type h2{
	position: absolute;
	top: 66px;
	right: 265px;
	font-size:36px;
	font-family:MyriadPro-Regular;
	font-weight:bold;
	color:rgba(0,0,0,1);
	line-height:60px;
}
.type .type_st{
	width: 100%;
	height: 645px;
	background-size: 100% 100%;
}
.type .type_st ul {
	width: 1198px;
	height: 525px;
	margin: 0 auto;
	padding-top: 60px;
}
.type .type_st ul li{
	width: 365px;
	height: 525px;
	float: left;
	border-radius:24px;
	box-shadow:2px 14px 46px rgba(0,0,0,0.07);
	margin-right: 50px;
}
.type .type_st ul li:last-child{
	margin-right: 0px;
}
.type .type_st ul li img{
	width: 100%;
	height: 439px;
	display: block;
}
.type .type_st ul li p{
	text-align: center;
	font-size:18px;
	font-family:SenticoSansDT-Light;
	font-weight:normal;
	color:rgba(0,0,0,1);
	padding-top: 28px;
}
</style>