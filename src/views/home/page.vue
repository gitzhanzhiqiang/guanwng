<template>
	<div class="homePage">
		<div class="banner">
			<el-carousel :interval="5000" arrow="always">
				<el-carousel-item v-for="item in url" :key="">
					<img :src="item.img1">
					<span>{{item.tit}}</span>
					<p>SIGN IN NOW</p>
				</el-carousel-item>
			</el-carousel>
		</div>
		<div class="titles">
			<h1>WHAT IS SUDFIN?</h1>
		</div>
		<div class="con">
			<div class="WHAT">
				<ul>
					<li v-for="itm in What">
						<img :src="itm.img1" />
						<p>{{itm.tit}}</p>
						<p>{{itm.tita}}</p>
						<i></i>
					</li>
				</ul>
			</div>
			<div class="SUNFIN">
				<p>SUNFIN is a comprehensive financial technology group .The company is founded by senior financial experts from Singapore, Hongkong and Southeast Asia, within veteran team of market research and professional financial planning, as well as rich practical experience in investment and financial management both home and abroad.</p>
			</div>
			<div class="btma">
				LEARN MORE
			</div>
		</div>
		<div class="our" :style="beijin">
			<h2>OUR ADWVANTAGES</h2>
			<div class="letter">
				<ul>
					<li class="wow flipInX bg-purple animated" v-for="itm in OUT" :class="{'actr': itm.status}" v-if='itm.status == true' v-on:mouseenter="getApplyList(itm)" v-on:mouseleave="getApplyList(itm)">
						<img :src="itm.img2" />
					</li>
					<li v-else v-on:mouseenter="getApplyList(itm)" v-on:mouseleave="getApplyList(itm)">
						<img :src="itm.img1" />
					</li>
				</ul>
			</div>
			<div class="letter_ti">
				<p>{{outtit}}</p>
				<ul>
					<li v-on:mouseenter="getApplyList(itm)" v-on:mouseleave="getApplyList(itm)" :class="{'abod': itm.status}" v-for="itm in OUT" @click="getApplyList(itm)">{{itm.tit}}</li>
				</ul>
			</div>
			<div class="btma">
				LEARN MORE
			</div>
		</div>
		<div class="TAILOR" :style="bejin">
			<h2>TAILOR-MADE FINANCIAL SERVICES FOR YOU</h2>
			<div class="TAILOR_letter">
				<ul>
					<li :class="{'srt': itm.status}" v-for="itm in TAILOR" @click="getApplyLista(itm)">
						<img :src="itm.img1" />
						<p>{{itm.tit}}</p>
					</li>

				</ul>
			</div>
			<div class="TAILOR_letterxia">
				<div class="imgb" :style="bejina">
					<img :src="imgimgs" />
				</div>
				<div class="imgtit">
					<h3>{{imgtit}}</h3>
					<p>{{imgtita}}</p>
					<a>LEARN MORE</a>
				</div>
			</div>
		</div>
		<div class="titles">
			<h1>NEWS INFORMATION</h1>
		</div>
		<div class="con">
			<div class="newd" :style="beijinc">
				<img src="~@res/imgd/nestu.png" />
				<div class="newd_lefe">
					<h2>NEWS HEADLINES NEWS HEADLINESNEWS HEADLINESNEWS HEADLINES</h2>
					<span>Aug 17,2018</span>
					<P>We will integrate global investment resources to tailor investment and financial solutions to our customers. We will integrate global investment resources to tailor investment and financial solutions to our customers.We will integrate global investment resources to tailor investment and financial solutions to our customers.We will integrate global investment resources to tailor investment and financial solu o tailor investment and financial solutions to our customers.We will integrate global investment resources to tailor investment and financial soluo tailor investment and financial solutions to our customers.We will integrate global investment resources to tailor investment and financial solu</P>
				</div>
				<div class="newd_right">
					<ul>
						<li>
							<h2>NEWS HEADLINES<span>Aug 17,2018</span></h2>
							<p>We will integrate global investment resources to tailor investment and financial solutions to our customers.</p>
						</li>
						<li>
							<h2>NEWS HEADLINES<span>Aug 17,2018</span></h2>
							<p>We will integrate global investment resources to tailor investment and financial solutions to our customers.</p>
						</li>
						<li>
							<h2>NEWS HEADLINES<span>Aug 17,2018</span></h2>
							<p>We will integrate global investment resources to tailor investment and financial solutions to our customers.</p>
						</li>
						<li>
							<h2>NEWS HEADLINES<span>Aug 17,2018</span></h2>
							<p>We will integrate global investment resources to tailor investment and financial solutions to our customers.</p>
						</li>
						<li>
							<h2>NEWS HEADLINES<span>Aug 17,2018</span></h2>
							<p>We will integrate global investment resources to tailor investment and financial solutions to our customers.</p>
						</li>

					</ul>
				</div>
			</div>
		</div>
		<div class="titles">
			<h1>OUR PARTNERS</h1>
		</div>
		<div class="con">
			<div class="cooperation">
				<ul>
					<li>
						<img src="~@res/imgd/hezuo/dongwu.png" />
					</li>
					<li>
						<img src="~@res/imgd/hezuo/uob.png" />
					</li>
					<li>
						<img src="~@res/imgd/hezuo/dbs.png" />
					</li>
					<li>
						<img src="~@res/imgd/hezuo/dawei.png" />
					</li>
					<li>
						<img src="~@res/imgd/hezuo/deheng.png" />
					</li>
				</ul>
			</div>
		</div>
	</div>
</template>
<script>
	import ajax from '@utils/config';
	import sowingMap from '@src/components/sowingMap';
	import { WOW } from 'wowjs';
	export default {
		components: {
			sowingMap
		},
		data() {

			var beijin = require("@res/imgd/beijin.png");
			var bejin = require("@res/imgd/bejin.png");
			var bejina = require("@res/imgd/bejina.png");
			var beijinc = require("@res/imgd/beijinc.png");
			return {
				params: {
					pageIndex: 1,
					pageSize: 12,
					platform: 'sunfin',
				},
				Various: {
					biaoti: 'Award planning for developers',
					zhang: require("@res/imgs/zhang.png"),
				},
				url: [{
						img1: require("@res/imgd/bannercc.png"),
						tit: 'S U N F I N is a comprehensive financial technology group',
					},
					{
						img1: require("@res/imgd/bannercc.png"),
						tit: 'S U N F I N is a comprehensive financial technology group',
					},
					{
						img1: require("@res/imgd/bannercc.png"),
						tit: 'S U N F I N is a comprehensive financial technology group',
					}
				],

				What: [{
						img1: require("@res/imgd/fan1.png"),
						tit: 'Senior market',
						tita: 'the research team',
					},
					{
						img1: require("@res/imgd/fan2.png"),
						tit: 'Professional financial',
						tita: 'planning team',
					},
					{
						img1: require("@res/imgd/fan3.png"),
						tit: 'Abundant overseas',
						tita: 'investment finance',
					}
				],

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
				TAILOR: [{
						img1: require("@res/imgd/hezuo/tal1.png"),
						tit: 'INVESTMENT MANAGEMENT',
						tita: 'We will integrate global investment resources to tailor investment and financial solutions to our customers.',
						img2: require("@res/imgd/baa.png"),
						status: true,
						id: 1,
					},
					{
						img1: require("@res/imgd/hezuo/tal2.png"),
						tit: 'TRUST SERVICE',
						tita: 'We will integrate global investment resources to tailor investment and financial solutions to our customers.ff',
						img2: require("@res/imgd/baa.png"),
						status: false,
						id: 2,
					},
					{
						img1: require("@res/imgd/hezuo/tal3.png"),
						tit: 'INSURANCE SERVICE',
						tita: 'We will integrate global investment resources to tailor investment and financial solutions to our customers.dd',
						img2: require("@res/imgd/baa.png"),
						status: false,
						id: 3,
					},
					{
						img1: require("@res/imgd/hezuo/tal4.png"),
						tit: 'ENTERPRISE FINANCING',
						tita: 'We will integrate global investment resources to tailor investment and financial solutions to our customers.aaa',
						img2: require("@res/imgd/baa.png"),
						status: false,
						id: 4,
					}
				],
				outtit: 'UNDERSTABDING THE GLOBAL MARKET CONTEXT',
				urla: 'https://img.zhaogu168.com/',
				imgimgs: require("@res/imgd/hezuo/tal1.png"),
				imgtit: 'INVESTMENT MANAGEMENT',
				imgtita: 'We will integrate global investment resources to tailor investment and financial solutions to our customers.',
				beijin: {
					backgroundImage: "url(" + beijin + ")",
				},
				bejin: {
					backgroundImage: "url(" + bejin + ")",
				},
				bejina: {
					backgroundImage: "url(" + bejina + ")",
				},
				beijinc: {
					backgroundImage: "url(" + beijinc + ")",
				},
				count: '0',
				vario: '1',
			}
		},
		computed: {},
		created() {
			this.setTime()
		},
		mounted() {
			new WOW().init()
		},
		methods: {
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
			getApplyLista(itm) {
				this.imgimgs = itm.img1
				this.imgtit = itm.tit
				this.imgtita = itm.tita
				this.TAILOR.map((item) => {
					if(item.id == itm.id) {
						item.status = true
					} else {
						item.status = false
					}
				})
			},
		},
		filters: {}
	}
</script>
<style lang="less" scoped>
	.el-carousel__item h3 {
		color: #475669;
		font-size: 18px;
		opacity: 0.75;
		line-height: 300px;
		margin: 0;
	}
	
	.banner {
		position: relative;
	}
	
	.banner .banner_wen {
		width: 1100px;
		height: 600px;
		border: 1px solid #000000;
		position: absolute;
		top: 0;
		left: 0;
		right: 0;
		bottom: 0;
		margin: auto;
	}
	
	.banner .banner_wen span {
		font-size: 21px;
		font-family: Montserrat-Regular;
		font-weight: 400;
		color: #000000;
	}
	
	.titles {
		position: relative;
	}
	
	.titles h1 {
		margin: 0 auto;
		text-align: center;
		font-size: 36px;
		font-family:MyriadPro-Regular;
		font-weight: normal;
		line-height: 68px;
		margin-top: 43px;
		background: white;
		margin-bottom: 30px;
	}
	/*WHAT*/
	
	.con .WHAT,
	.con .SUNFIN {
		width: 100%;
		overflow: hidden;
	}
	
	.con .WHAT ul li {
		width: 398px;
		overflow: hidden;
		float: left;
		position: relative;
		margin-bottom: 77px;
	}
	
	.con .WHAT ul li img {
		width: 108px;
		height: 108px;
		display: block;
		margin: 0 auto;
		margin-bottom: 30px;
	}
	
	.con .WHAT ul li p {
		text-align: center;
		font-size:20px;
		font-family:MicrosoftYaHeiLight;
		font-weight: 400;
		color: rgba(0, 0, 0, 1);
	}
	
	.con .WHAT ul li i {
		width: 2px;
		height: 180px;
		display: block;
		position: absolute;
		border-right: 1px dashed #CCCCCC;
		right: 0;
		top: 10px;
	}
	
	.con .WHAT ul li:last-child i {
		right: -5px;
	}
	
	.con .SUNFIN {
		width: 1200px;
		height: 210px;
		background: rgba(255, 255, 255, 1);
		border-radius: 8px;
		box-shadow: 5px 0px 32px rgba(0, 0, 0, 0.08);
	}
	
	.con .SUNFIN p {
		width:910px;
		font-size:16px;
		font-family:SenticoSansDT-Light;
		font-weight: 300;
		color: rgba(114, 118, 154, 1);
		text-align: center;
		margin: 0 auto;
		padding-top: 74px;
		line-height: 25px;
	}
	
	.con .btma {
		width: 260px;
		height: 60px;
		border: 1px solid rgba(153, 153, 153, 1);
		border-radius: 30px;
		text-align: center;
		line-height: 60px;
		font-size: 14px;
		font-family:MyriadPro-Regular;
		font-weight: 400;
		color: rgba(153, 153, 153, 1);
		margin: 0 auto;
		margin-top: 61px;
		margin-bottom: 100px;
	}
	/*our*/
	
	.our {
		width: 100%;
		height: 798px;
		background-size: 100% 100%;
	}
	
	.our h2,
	.TAILOR h2 {
		text-align: center;
		font-size: 36px;
		font-family:MyriadPro-Regular;
		font-weight: bold;
		color: rgba(255, 255, 255, 1);
		line-height: 36px;
		padding-top: 68px;
		padding-bottom: 77px;
	}
	
	.our .letter {
		width: 1200px;
		overflow: hidden;
		margin: 0 auto;
		margin-bottom: 53px;
	}
	
	.our .letter ul li {
		width: 170px;
		height: 185px;
		float: left;
		margin-right: 165px;
		cursor: pointer;
	}
	
	.our .letter ul li img {
		width: 170px;
		height: 185px;
		display: block;
	}
	
	.our .letter ul li:last-child {
		margin-right: 0px;
	}
	
	.our .letter_ti {
		width: 1200px;
		height: 210px;
		background: rgba(255, 255, 255, 0.88);
		border-radius: 8px;
		box-shadow: 5px 0px 32px rgba(0, 0, 0, 0.08);
		margin: 0 auto;
	}
	
	.our .letter_ti p {
		float: left;
		font-size: 20px;
		font-family:Verdana;
		font-weight: 400;
		color: rgba(0, 0, 0, 1);
		margin-left: 86px;
		margin-top: 84px;
	}
	
	.our .letter_ti ul {
		float: right;
		overflow: hidden;
		margin-right: 113px;
		margin-top: 40px;
	}
	
	.our .letter_ti ul li {
		width: 400px;
		font-size: 14px;
		font-family:SenticoSansDT-Light;
		font-weight: 400;
		color: rgba(106, 110, 142, 1);
		line-height: 25px;
		margin-bottom: 15px;
		text-align: center;
		cursor: pointer;
	}
	
	.our .letter_ti ul li.abod {
		font-size: 16px;
		color: rgba(52, 63, 167, 1);
	}
	
	.our .btma {
		width: 260px;
		height: 60px;
		border: 1px solid white;
		border-radius: 30px;
		text-align: center;
		line-height: 60px;
		font-size: 14px;
		font-family:MyriadPro-Regular;
		font-weight: 400;
		color: white;
		margin: 0 auto;
		margin-top: 61px;
		margin-bottom: 100px;
	}
	
	.TAILOR {
		width: 100%;
		height: 950px;
		background-size: 100% 100%;
	}
	
	.TAILOR h2 {
		color: #000000;
	}
	
	.TAILOR .TAILOR_letter {
		width: 1200px;
		overflow: hidden;
		margin: 0 auto;
	}
	
	.TAILOR .TAILOR_letter ul li {
		width: 290px;
		overflow: hidden;
		float: left;
		margin-left: 10px;
		cursor: pointer;
	}
	
	.TAILOR .TAILOR_letter ul li.srt {
		border-bottom: 1px solid #B4B6D2;
	}
	
	.TAILOR .TAILOR_letter ul li img {
		width: 114px;
		height: 114px;
		display: block;
		margin: 0 auto;
		margin-bottom: 21px;
	}
	
	.TAILOR .TAILOR_letter ul li p {
		text-align: center;
		font-size: 18px;
		font-family:SenticoSansDT-Light;
		font-weight: 400;
		color: rgba(0, 0, 0, 1);
		margin-bottom: 60px;
	}
	
	.TAILOR .TAILOR_letterxia {
		width: 1200px;
		height: 410px;
		background: rgba(255, 255, 255, 1);
		border-radius: 8px;
		box-shadow: 5px 0px 32px rgba(0, 0, 0, 0.1);
		margin: 0 auto;
	}
	
	.TAILOR .TAILOR_letterxia .imgb {
		float: left;
		width: 477px;
		height: 100%;
	}
	
	.TAILOR .TAILOR_letterxia .imgb img {
		width: 242px;
		height: 242px;
		display: block;
		float: right;
		margin-top: 69px;
		margin-right: 88px;
	}
	
	.TAILOR .TAILOR_letterxia .imgtit {
		width: 600px;
		height: 100%;
		float: left;
		margin-left: 50px;
		position: relative;
	}
	
	.TAILOR .TAILOR_letterxia .imgtit h3 {
		font-size: 20px;
		font-family:SenticoSansDT-Light;
		font-weight: 400;
		color: rgba(0, 0, 0, 1);
		line-height: 25px;
		padding-top: 109px;
		margin-bottom: 39px;
	}
	
	.TAILOR .TAILOR_letterxia .imgtit p {
		font-size: 16px;
		font-family:SenticoSansDT-Light;
		font-weight: 300;
		color: rgba(114, 118, 154, 1);
		line-height: 25px;
	}
	
	.TAILOR .TAILOR_letterxia .imgtit a {
		position: absolute;
		bottom: 100px;
		right: 0px;
		cursor: pointer;
		font-size: 14px;
		font-family: MicrosoftYaHei;
		font-weight: 400;
		color: rgba(102, 110, 209, 1);
	}
	/*newd*/
	
	.newd {
		width: 100%;
		height: 911px;
		background: 100% 100%;
		box-shadow: 5px 5px 24px rgba(0, 0, 0, 0.3);
		margin: 0 auto;
		margin-top: 30px;
		margin-bottom: 125px;
	}
	
	.newd img {
		width: 100%;
		height: 415px;
		display: block;
	}
	
	.newd .newd_lefe {
		width: 580px;
		overflow: hidden;
		float: left;
	}
	
	.newd .newd_lefe h2 {
		width: 490px;
		font-size: 20px;
		font-family:SenticoSansDT-Light;
		font-weight: 300;
		color: rgba(0, 0, 0, 1);
		margin: 0 auto;
		margin-top: 56px;
	}
	
	.newd .newd_lefe span {
		width: 490px;
		font-size: 12px;
		font-family: MicrosoftYaHeiLight;
		font-weight: 300;
		color: rgba(153, 153, 153, 1);
		margin: 0 auto;
		display: block;
		margin-top: 23px;
		margin-bottom: 18px;
	}
	
	.newd .newd_lefe p {
		width: 490px;
		font-size: 14px;
		font-family:SenticoSansDT-Light;
		font-weight: 300;
		color: rgba(153, 153, 153, 1);
		margin: 0 auto;
	}
	
	.newd .newd_right {
		width: 617px;
		height: 490px;
		overflow-y: auto;
		float: right;
	}
	
	.newd .newd_right ul li {
		width: 100%;
		height: 159px;
		border-bottom: 1px dashed #9D99E8;
	}
	
	.newd .newd_right ul li h2 {
		width: 490px;
		font-size: 20px;
		font-family: MicrosoftYaHeiLight;
		font-weight: 300;
		color: rgba(0, 0, 0, 1);
		margin: 0 auto;
		padding-top: 36px;
		margin-bottom: 28px;
		cursor: pointer;
	}
	
	.newd .newd_right ul li h2 span {
		float: right;
		font-size: 12px;
		font-family: MicrosoftYaHeiLight;
		font-weight: 300;
		color: rgba(153, 153, 153, 1);
		margin-top: 6px;
	}
	
	.newd .newd_right ul li p {
		width: 490px;
		font-size: 14px;
		font-family:SenticoSansDT-Light;
		font-weight: 300;
		color: rgba(153, 153, 153, 1);
		margin: 0 auto;
		text-overflow: ellipsis;
		display: -webkit-box;
		-webkit-box-orient: vertical;
		-webkit-line-clamp: 2;
		overflow: hidden;
	}
	/*合作伙伴*/
	
	.cooperation {
		width: 100%;
		overflow: hidden;
		margin-top: 50px;
		margin-bottom: 77px;
	}
	
	.cooperation ul li {
		width: 240px;
		overflow: hidden;
		float: left;
	}
	
	.cooperation ul li img {
		display: block;
		margin: 0 auto;
	}
</style>