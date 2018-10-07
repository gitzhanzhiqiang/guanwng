<template>
    <div class="ggg_user">
       <div class="banner">
			<img :src="img1">
			<P>AN OPEN-SOURCE FAIR<br /> 
FREE BLOCK CHAIN <br /> 
APPLICATION PLATFORM</P>
		</div>
		<div class="con">
			<div class="introduce">
				<h1>OUR ADVANTAGES</h1>
				<div class="getad">
					<ul>
						<li class="wow flipInX bg-purple animated" v-for="itm in OUT" :class="{'actr': itm.status}" v-if='itm.status == true' v-on:mouseenter="getApplyList(itm)" v-on:mouseleave="getApplyList(itm)">
							<img :src="itm.img2" />
						</li>
						<li v-else v-on:mouseenter="getApplyList(itm)" v-on:mouseleave="getApplyList(itm)">
							<img :src="itm.img1" />
						</li>
					</ul>
				</div>
				<h2>ONE STOP FINANCIAL SERVICES</h2>
				<p>We offer one-stop, professional and rounded financial services, including financial planning, fund management, risk management, various insurance and overseas investment planning. We  multi-dimensionally assess customer’s financial needs, qualitativly and quantitatively analyze and confirm investment objectives, and then timely follow-up market conditions for risk management.</p>
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
        	img1: require("@res/imgd/bannercc.png"),
        	OUT: [{
						img1: require("@res/imgd/bta.png"),
						tit: 'UNDERSTABDING THE GLOBAL MARKET CONTEXT',
						img2: require("@res/imgd/baa.png"),
						status: true,
						id: 1,
					},
					{
						img1: require("@res/imgd/btb.png"),
						tit: 'UNDERSTABDING THE GLOBAL MARKET CONTEXT',
						img2: require("@res/imgd/baa.png"),
						status: false,
						id: 2,
					},
					{
						img1: require("@res/imgd/btc.png"),
						tit: 'UNDERSTABDING THE GLOBAL MARKET CONTEXT4',
						img2: require("@res/imgd/baa.png"),
						status: false,
						id: 3,
					},
					{
						img1: require("@res/imgd/btd.png"),
						tit: 'UNDERSTABDING THE GLOBAL MARKET CONTEXT0',
						img2: require("@res/imgd/baa.png"),
						status: false,
						id: 4,
					}
				],
        }
    },
    computed: {

    },
    created() {
    	this.fanding()
    	this.setTime()
    },
    mounted() {
    	new WOW().init() 
    },
    methods: {
    	fanding(){
				window.scrollTo(0,0);
			},
			getApplyList(itm) {
				this.outtit = itm.tit
				this.count = itm.id
				this.OUT.map((item) => {
					if(item.id == itm.id) {
						item.status = true
					} else {
						item.status = false
					}
				})
			},
			setTime() {
				this.timer = setInterval(() => {
					this.count++;
					if(this.count == 5) {
						this.count = 1
					}
					this.OUT.map((item) => {
						if(item.id == this.count) {
							this.getApplyList(item)
						}
					})
				}, 2500)
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
.introduce{
	width: 100%;
	overflow: hidden;
}
.introduce h1{
	font-size:36px;
	font-family:MyriadPro-Regular;
	font-weight:bold;
	color:rgba(0,0,0,1);
	line-height:36px;
	text-align: center;
	padding: 82px 0px 105px 0px;
}
.getad {
	width:1190px;
	height:138px;
	background:rgba(255,255,255,1);
	opacity:0.88;
	border-radius:8px;
	box-shadow:5px 0px 32px rgba(0,0,0,0.08);
	margin-bottom: 72px;
}
.getad ul li{
	width: 86px;
	height: 93px;
	float: left;
	margin-left: 170px;
	margin-top: 20px;
}
.getad ul li img{
	width: 86px;
	height: 93px;
}
.introduce h2{
	font-size:20px;
	font-family:SenticoSansDT-Light;
	font-weight:bold;
	color:rgba(0,0,0,1);
	margin-bottom: 39px;
}
.introduce p{
	font-size:16px;
font-family:SenticoSansDT-Light;
font-weight:normal;
color:rgba(51,51,51,1);
line-height: 30px;
margin-bottom: 150px;
}
</style>


