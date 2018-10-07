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
				<h1>OUR MISSION</h1>
				<p>Based on Singapore, have the whole world in view. </p>
				<p>Provide one-stop flexible professional solutions for individuals and corporate customers by diversified business platforms of the Group.</p>
				<p>Professional team can afford reliable financial advisory services to customers, and helps customers get a full return.</p>
				<P>Through qualitative and quantitative analysis, we focus on the core financial needs of our customers. We breakdown the single situation of product and market, screening global investment products for customers in multi-dimensional manner. Meanwhile, we customize asset allocation portfolio which is specialized, personalized and comprehensive.</P>
				<P>We are aiming to create maximum value for investors and reach a win-win situation at last.</P>
				<P>Based on the world, our professional team are looking for innovative sustainable high-quality products, building barrier-free investment channels, so that customers can seize the market opportunities in advance, and reach more achievements of customers’ wealth.</P>
				<P>Our customers can enjoy more outstanding experience. We not only manage the wealth of customers, but also arrange a series of exclusive and honorable services and events, including, but not limited to, special bus reception, point-to-point support services.</P>
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
.introduce p{
	font-size:16px;
	font-family:SenticoSansDT-Light;
	font-weight:normal;
	color:rgba(0,0,0,1);
	text-align: left;
	margin-bottom: 70px;
	line-height: 30px;
}
.introduce img{
	width: 100%;
	height: 200px;
	margin-bottom: 78px;
}
</style>


