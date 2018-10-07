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
				<h1>SUNFIN</h1>
				<p>A financial technology group that provides diversified financial services.</p>
				<p>SUNFIN is a comprehensive financial technology group which is contributed to provide diversified financial service to global customers in order to meet their needs in all aspects of investment. The company is founded by senior financial experts from Singapore, Hongkong and Southeast Asia, within veteran team of market research and professional financial planning, as well as rich practical experience in investment and financial management both home and abroad.</p>
				<p>Global financial products from the group meet customers' pressing needs ranging from overseas fund investment, wealth inheritance, Life insurance, retirement planning to personal health management, overseas life plan, children overseas education and so on, aiming to afford all scope of guarantee to customers and their loves.</p>
				<img :src="aboutimg"/>
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
        	aboutimg: require("@res/imgd/aboutimg.png"),
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


