<template>
    <div class="app-container calendar-list-container servicePage">
       <div class="banner">
			<img :src="img1">
			<div class="btm" @click="go_url" style="cursor:pointer ;">
				APPLY NOW
			</div>
			<p>TRUST SERVICE<br />Financial services for people <br />
with high net worth and their families.</p>
		</div>
		<div class="con">
			<div class="Trust">
				Trust is one of the financial services only provided to high net-worth individuals and families aiming to effectively <br />
protect the value and inheritance through the establishment of a special asset management system. <br />
The Group provides a wide range of professional trust programs designed to meet needs of the wealth inheritance of individuals and families.
			</div>
			<div class="titd">
				<h1>THE SERVICE PROCESS INCLUDES</h1>
			</div>
			<div class="these">
				<ul>
					<li :style="beijind">
						<img style="width:196px;height:140px;padding: 70px 0px 65px 0px;"  src="~@res/imgd/these1.png"/>
						<h2>REAL ESTATE</h2>
						<p>ooking for real estate projects with great potential for value growth around the world and taking advantage of the investment opportunities in the first-hand market.</p>
					</li>
					<li :style="beijind">
						<img style="width:196px;height:180px;padding: 50px 0px 45px 0px;" src="~@res/imgd/these2.png"/>
						<h2>REAL ESTATE</h2>
						<p>ooking for real estate projects with great potential for value growth around the world and taking advantage of the investment opportunities in the first-hand market.</p>
					</li>
					<li :style="beijind">
						<img style="width:165px;height:196px;padding: 50px 0px 35px 0px;" src="~@res/imgd/these3.png"/>
						<h2>REAL ESTATE</h2>
						<p>ooking for real estate projects with great potential for value growth around the world and taking advantage of the investment opportunities in the first-hand market.</p>
					</li>
				</ul>
			</div>
		</div>
    </div>
</template>
<script>
	 import {WOW} from 'wowjs';
import ajax from '@utils/config';
export default {
    data() {
    	var beijind = require("@res/imgd/beijind.png");
        return {
          img1: require("@res/imgd/bannercc.png"),
          beijind:{
          	backgroundImage: "url(" + beijind + ")",
          },
        }
    },
    computed: {
    },
    created() {
    	this.fanding()
    },
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
    filters: {
    }
}
</script>
<style lang="less" scoped>
.titd h1{
	padding: 50px 0 60px 0px;
}
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
	.Trust {
		width: 1200px;
		overflow: hidden;
		margin: 0 auto;
		text-align: center;
		font-size:16px;
		font-family:SenticoSansDT-Light;
		font-weight:normal;
		color:#464646;
		line-height: 25px;
		padding: 80px 0px 0px 0px;
	}
	.these{
		width: 100%;
		overflow: hidden;
		margin-bottom: 70px;
	}
	.these ul li{
		width: 362px;
		height: 549px;
		background-size: 100% 100%;
		float: left;
		margin-right: 55px;
	}
	.these ul li:last-child{
		margin-right: 0px;
	}
	.these ul li img{
		display: block;
		margin: 0 auto;
	}
	.these ul li h2{
		width:240px;
		font-size:20px;
		font-family:SenticoSansDT-Light;
		font-weight:bold;
		color:rgba(0,0,0,1);
		margin: 0 auto;
		padding: 0px 0px 30px 0px;
	}
	.these ul li p{
		width:240px;
		font-size:16px;
		font-family:SenticoSansDT-Light;
		font-weight:normal;
		color:rgba(0,0,0,1);
		margin: 0 auto;
		line-height: 30px;
		text-overflow: ellipsis;
	    display: -webkit-box;
	    -webkit-box-orient: vertical;
	    -webkit-line-clamp: 5;
	    overflow: hidden;
	}
</style>


