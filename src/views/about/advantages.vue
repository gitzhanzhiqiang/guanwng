<template>
    <div class="ggg_user">
       <div class="banner">
			<img :src="img1">
			<P>AN OPEN-SOURCE FAIR<br /> 
FREE BLOCK CHAIN <br /> 
APPLICATION PLATFORM</P>
		</div>
		<div class="con">
			<div class="Partner">
				<h2 class="cent">WHAT IS GOLD ORE?</h2>
				<p>We are dedicated to the development and application of the block chain technology. Aiming to design a practical and meaningful application of block chain with developers, Gold Ore provides an open source platform to block chain technology enthusiasts as well as given technical assistance, so that developers can fully play their all talent and imagination. Meanwhile, a non-developer can enjoy the fun from block chain technology as a user, because our services are towards to all.</p>
			</div>
			<div class="follows">
				<ul>
					<li>
						<b>	
							<span class="time">2697</span>
							<span class="Tril">Trillions</span>
						</b>
						<img src="~@res/imgs/imga/touying.png"/>
						<p style="padding-top: 200px;">Global AI market size in</p>
						<p>2018</p>
					</li>
					<li>
						<b>	
							<span class="time">55<a>%</a></span>
						</b>
						<img src="~@res/imgs/imga/touying.png"/>
						<p style="padding-top: 200px;">55% compound annual</p>
						<p>rate of growth in future</p>
					</li>
					<li>
						<b>	
							<span class="time">10</span>
							<span class="Tril">Trillions</span>
						</b>
						<img src="~@res/imgs/imga/touying.png"/>
						<p style="padding-top: 200px;">Market size of encrypted</p>
						<p>digital currency and block</p>
						<p>chain can reach 10 trillion USD dolla</p>
					</li>
				</ul>
			</div>
		</div>
    </div>
</template>
<script>
import ajax from '@utils/config';
import {WOW} from 'wowjs';
export default {
    data() {
        return {
        	img1: require("@res/imgs/imga/aboutdb.jpg"),
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
    	fanding(){
				window.scrollTo(0,0);
			},
    },
    filters: {
    }
}
</script>
<style lang="less" scoped>
.banner{
 	position: relative;
 }
 .banner img{
		width: 100%;
		height: 100%;
	}
  .banner P{
		font-size:50px;
		font-family:MyriadPro-Regular;
		font-weight:bold;
		color:rgba(255,255,255,1);
		line-height:73px;
		position: absolute;
		left: 399px;
		bottom: 220px;
 }
.Partner {
	width: 100%;
	overflow: hidden;
	margin-bottom: 40px;
}
.Partner P{
	width:918px;
	font-size:16px;
	font-family:ArialMT;
	font-weight:400;
	color:#808080;
	line-height: 25px;
	margin: 0 auto;
}
.follows{
	width: 1100px;
	overflow: hidden;
	margin-bottom: 60px;
}

.follows ul{
	overflow: hidden;
	margin-bottom: 15px;
}
.follows ul li{
	width: 365px;
	height: 300px;
	float: left;
	position: relative;
}
.follows ul li b{
	width: 163px;
	height: 163px;
	background: url(images/qiu.png) no-repeat;
	background-size: 100% 100%;
	display: block;
	margin: 0 auto;
	visibility: visible;
    animation-duration: 2s;
    animation-delay: 300ms;
    animation-iteration-count: infinite;
    animation-name: pulse;
    position: absolute;	
    z-index: 22;
    left: 95px;
    top: 14px;
}
.follows ul li b .time{
	display: block;
	font-size:50px;
	font-family:PingFangSC-Semibold;
	font-weight:600;
	color:rgba(255,255,255,1);
	text-align: center;
	padding-top: 40px;
}
.follows ul li b .time a{
	font-size:24px;
	font-family:PingFangSC-Semibold;
	font-weight:600;
	color:rgba(255,255,255,1);
	line-height:14px;
	margin-left: 5px;
}
.follows ul li b .Tril{
	font-size:19px;
	font-family:PingFangSC-Light;
	font-weight:300;
	color:rgba(255,255,255,1);
	line-height:30px;
	display: block;
	text-align: center;
}
.follows ul li p{
	font-size:16px;
	font-family:ArialMT;
	font-weight:400;
	color:rgba(124,124,139,1);
	line-height:25px;
	margin: 0 auto;
	text-align: center;
}
.follows ul li img{
		display: block;
		width:227px;
		height:225px;
		position: absolute;
		z-index: 0;
	    top: 30px;
	    left: 130px;
	}
</style>


