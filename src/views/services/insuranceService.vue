<template>
	<div class="ggg_user">
		<div class="banner">
			<img :src="img1">
			<div class="btm" @click="go_url" style="cursor:pointer ;">
				APPLY NOW
			</div>
			<p>THIS PLANNING HAS BEEN STARTED.<br />JOTN US NOW!!</p>
		</div>
		<div class="con">
			<div class="well">
				<p style="margin-bottom: 25px;">It well known that capital is the premise for the survival and development of enterprise groups. Especially, financing of enterprise groups is<br /> more complicated than that of individual enterprises.</p>
				<p>From the perspective of the group as a whole, the focus of its financing management is mainly on the following four aspects:</p>
			</div>
			<div class="digital">
				<ul>
					<li :style="chan1">
						<a>1</a>
						<p>dealing with the relationship between the group and the capital structure of the group members;</p>
					</li>
					<li :style="chan2">
						<a>2</a>
						<p>dealing with the relationship between the group and the capital structure of the group members;</p>
					</li>
					<li :style="chan3">
						<a>3</a>
						<p>dealing with the relationship between the group and the capital structure of the group members;</p>
					</li>
					<li :style="chan4">
						<a>4</a>
						<p>dealing with the relationship between the group and the capital structure of the group members;</p>
					</li>
				</ul>
			</div>
			
			<div class="corporate">
				<h3>OUR CORPORATE FINANCE SERVICES FOR CUSTOMERS IS SHOWN AS BELOW</h3>
				<p>Listing sponsorship</p>
				<p>On the term of enterprise financial transaction, such as mergers and acquisitions, we will provide professional analysis of listing rules<br /> and acquisition rules</p>
				<p>Stock and / or bond raising<br />
Activities, fund-raising and other suggestions</p>
			</div>
		</div>
	</div>
</template>
<script>
	 import {WOW} from 'wowjs';
	import ajax from '@utils/config';
	export default {
		data() {
			var chan1 = require("@res/imgd/chan1.png");
			var chan2 = require("@res/imgd/chan2.png");
			var chan3 = require("@res/imgd/chan3.png");
			var chan4 = require("@res/imgd/chan4.png");
			return {
				img1: require("@res/imgd/bannercc.png"),
				chan1:{backgroundImage: "url(" + chan1 + ")",},
				chan2:{backgroundImage: "url(" + chan2 + ")",},
				chan3:{backgroundImage: "url(" + chan3 + ")",},
				chan4:{backgroundImage: "url(" + chan4 + ")",},
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
	.well{
		margin-top: 80px;
		margin-bottom: 70px;
	}
	.well p{
		text-align: center;
		font-size:16px;
		font-family:SenticoSansDT-Light;
		font-weight:normal;
		color:rgba(0,0,0,1);
		line-height: 30px;
	}
	.digital {
		width: 100%;
		overflow: hidden;
		margin: 0 auto;
	}
	.digital ul li{
		width: 230px;
		height: 500px;
		background-size: 100% 100%;
		position: relative;
		float: left;
		margin-right: 93px;
	}
	.digital ul li:last-child{
		margin-right: 0px;
	}
	.digital ul li a{
		width:60px;
		height:60px;
		background:rgba(101,136,236,1);
		border-radius:50%;
		display: block;
		position: absolute;
		top: 0px;
		left: 0px;
		right: 0px;
		bottom: 0px;
		margin: auto;
		line-height: 60px;
		font-size:40px;
		font-family:SenticoSansDT-Light;
		font-weight:normal;
		color:rgba(255,255,255,1);
		text-align: center;
	}
	.digital ul li p{
		width: 205px;
		font-size:16px;
		font-family:SenticoSansDT-Light;
		font-weight:normal;
		word-break:break-all;
		text-align: center;
		text-overflow: ellipsis;
	    display: -webkit-box;
	    -webkit-box-orient: vertical;
	    -webkit-line-clamp: 4;
	    overflow: hidden;
	    position: absolute;
	    bottom: 60px;
	    left: 13px;
	}
	.digital ul li:nth-child(even) p{
		color:#1f1f21;
	}
	.digital ul li:nth-child(odd) p{
		color:rgba(255,255,255,1);
	}
	.corporate {
		width:100%;
		overflow: hidden;
		margin: 0 auto;
	}
	.corporate h3{
		text-align: center;
		font-size:20px;
		font-family:SenticoSansDT-Light;
		font-weight:bold;
		color:rgba(0,0,0,1);
		padding: 80px 0px 40px 0px;
	}
	.corporate p{
		font-size:16px;
		font-family:SenticoSansDT-Light;
		font-weight:normal;
		color:rgba(0,0,0,1);
		text-align: center;
		line-height: 25px;
		margin-bottom: 30px;
	}
</style>