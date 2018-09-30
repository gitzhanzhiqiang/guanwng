<template>
	<div class="app-container calendar-list-container ggg_user">
		<div class="con">
			<div class="partners">
				<h1>OUR PARTNERS</h1>
				<ul>
					<li>
						<img src="~@res/imgd/hezuo/dongwu.png" />
						<h2>SOOCHOW SECURITIES CO. LTD</h2>
						<p>SOOCHOW SECURITIES CO., LTD is a comprehensive securities company having all securities operation licenses. All this time, SOOCHOW SECURITIES has persisted in stringent management, steady running and standard operation, and established a business system with securities brokerage, investment banking, asset management, securities finance, securities investment and Internet finance as basic architecture, and an operation support system of research consulting, information technology and risk management, creating a co-development and win-win cooperation future for customers .</p>
					</li>
					<li>
						<img src="~@res/imgd/hezuo/uob.png" />
						<h2>UOB BANK</h2>
						<p>UOB is committed to building lasting relationships with customers, through product and market expertise, and promise to always do what is right.
With a well-established global presence today and particularly in Asia, UOB has understanding of Asian markets, corporate culture and business mindsets, which is matched by few. Their strong foothold in Singapore, Malaysia, Indonesia, Thailand and China is well-placed to create greater access and growth in this region, for customers.</p>
					</li>
					<li>
						<img src="~@res/imgd/hezuo/dbs.png" />
						<h2>DBS BANK</h2>
						<p>DBS, a leading financial services group headquartered in Singapore, operates across 18 markets.They are an Asia-centric commercial bank focused on harnessing the region’s long-term potential as the centre of economic gravity shifts eastwards to Asia.</p>
					</li>
					<li>
						<img src="~@res/imgd/hezuo/dawei.png" />
						<h2>DENTONS RODYK & DAVIDSON LLP</h2>
						<p>Dentons Rodyk & Davidson LLP works as one of Singapore’s oldest legal practices, trusted since 1861 by clients near and far, rely on its full service capabilities to help clients achieve their business goals in Singapore and throughout Asia. Consistently ranked in leading publications, its legal teams regularly represent a diverse clientele in a broad spectrum of industries and businesses.</p>
					</li>
					<li>
						<img src="~@res/imgd/hezuo/deheng.png" />
						<h2>DEHENG LAW OFFICES</h2>
						<p>Ethics and integrity are important to DeHeng professionals who aim to protect the legitimate rights and interests of their clients and achieve goals of social fairness and justice. With over 20 years of experience, DeHeng has developed a broad client base and a service network with branches and professionals in many key cities.</p>
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
//			fsfdf (name) {
//				console.log(this.$refs[name])
//			}
		},
		filters: {}
	}
</script>
<style lang="less" scoped>
.banner{
 	position: relative;
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
 .banner img{
		width: 100%;
		height: 100%;
	}
	.partners {
		width: 100%;
		overflow: hidden;
	}
	.partners h1{
		font-size:36px;
		font-family:MyriadPro-Regular;
		font-weight:bold;
		color:rgba(0,0,0,1);
		line-height:36px;
		text-align: center;
		padding: 150px 0px 0px 0px;
	}
	.partners ul li{
		border-bottom: 1px solid #CCCCCC;
	}
	.partners ul li:last-child{
		border-bottom:none;
	}
	.partners ul li h2{
		font-size:20px;
		font-family:SenticoSansDT-Light;
		font-weight:bold;
		color:rgba(0,0,0,1);
		padding: 0px 0px 38px 0px;
	}
	.partners ul li img{
		margin: 0 auto;
		display: block;
		padding: 72px 0px 49px 0px;
	}
	.partners ul li p{
		font-size:16px;
		font-family:SenticoSansDT-Light;
		font-weight:normal;
		color:#333333;
		line-height: 25px;
		margin-bottom: 79px;
		text-overflow: ellipsis;
		display: -webkit-box;
		-webkit-box-orient: vertical;
		-webkit-line-clamp: 4;
		overflow: hidden;
	}
</style>