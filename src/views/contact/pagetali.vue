<template>
	<div class="app-container calendar-list-container ggg_user">
		<div class="con">
			<div class="pplyfor">
				<div class="choose">
					<p>APPLICATION APPROVED</p>
				</div>
				<div class="information">
					<div class="information_ti">
						<div class="information_ta">
							<p>We have sent a successful SMS to your</p>
							<p>telephone number
								<a style="font-size: 24px;color: #000000;">{{rowData}}</a>
							</p>
							<span>Did not receive SMS?</span>
							<div class="bim">
								<el-button type="primary" class='btmz'>RE SEND</el-button>
								<el-button type="primary" class='btmy'>SENDING TO E-MAIL</el-button>
							</div>
						</div>
						<b>If there are other questions, please scan the bottom two dimensional code to contact our official customer service.</b>
						<el-button type="primary" @click="$router.push('/sunfin/index')" round>HOMEPAGE</el-button>
					</div>

				</div>
			</div>
		</div>
	</div>
</template>
<script>
	import ajax from '@utils/config';
	export default {
		data() {
			return {
				rowData:'',
				
			}
		},
		computed: {

		},
		created() {
			let data = this.$route.query.data ? JSON.parse(this.$route.query.data) : '';
			 this.rowData = data
			this.fanding()
		},
		mounted() {},
		methods: {
			fanding() {
				window.scrollTo(0, 0);
			},
		},
		filters: {}
	}
</script>
<style lang="less" scoped>
	.pplyfor {
		width: 100%;
		height: 900px;
		position: relative;
		margin-top: 100px;
	}
	
	.pplyfor .information {
		width: 1000;
		height: 800px;
		background: rgba(255, 255, 255, 1);
		border: 1px solid rgba(72, 134, 239, 1);
		margin: 0 auto;
	}
	
	.pplyfor .information .information_ti {
		width: 100%;
		overflow: hidden;
		margin: 0 auto;
		padding-top: 126px;
	}
	
	.pplyfor .information .information_ti button {
		width: 359px;
		display: block;
		margin: 0 auto;
	}
	
	.pplyfor .information .information_ti b {
		width: 608px;
		font-size: 14px;
		font-family: MicrosoftYaHei;
		font-weight: 400;
		color: rgba(153, 153, 153, 1);
		display: block;
		margin: 0 auto;
		line-height: 25px;
		margin-bottom: 46px;
	}
	
	.pplyfor .information .information_ti .information_ta {
		width: 800px;
		height: 360px;
		margin: 0 auto;
		background: rgba(255, 255, 255, 1);
		box-shadow: 0px 0px 13px rgba(35, 24, 21, 0.09);
		margin-bottom: 54px;
	}
	
	.pplyfor .information .information_ti .information_ta p {
		width: 495px;
		margin: 0 auto;
		font-size: 24px;
		font-family: MicrosoftYaHei;
		font-weight: 400;
		color: rgba(153, 153, 153, 1);
		line-height: 45px;
	}
	
	.pplyfor .information .information_ti .information_ta p:first-child {
		padding-top: 50px;
	}
	
	.pplyfor .information .information_ti .information_ta span {
		font-size: 14px;
		font-family: MicrosoftYaHei;
		font-weight: 400;
		color: rgba(153, 153, 153, 1);
		width: 495px;
		margin: 0 auto;
		line-height: 30px;
		display: block;
		margin-top: 50px;
	}
	
	.pplyfor .information .information_ti .information_ta .bim {
		width: 495px;
		margin: 0 auto;
		margin-top: 24px;
	}
	
	.pplyfor .information .information_ti .information_ta .bim .btmz {
		width: 160px;
		height: 40px;
		background: rgba(255, 255, 255, 1);
		border: 1px solid rgba(72, 134, 239, 1);
		font-size: 14px;
		font-family: MicrosoftYaHei-Bold;
		font-weight: bold;
		color: rgba(72, 134, 239, 1);
		float: left;
	}
	
	.pplyfor .information .information_ti .information_ta .bim .btmy {
		width: 280px;
		height: 40px;
		background: rgba(255, 255, 255, 1);
		border: 1px solid rgba(72, 134, 239, 1);
		font-size: 14px;
		font-family: MicrosoftYaHei-Bold;
		font-weight: bold;
		color: rgba(72, 134, 239, 1);
		float: right;
	}
	
	.pplyfor .choose {
		width: 800px;
		height: 100px;
		position: absolute;
		top: -50px;
		left: 145px;
	}
	
	.pplyfor .choose p {
		float: left;
		width: 800px;
		height: 100px;
		line-height: 100px;
		text-align: center;
		font-family: MicrosoftYaHei-Bold;
		font-weight: bold;
		color: white;
		background: #4886EF;
		box-shadow: 0px 0px 13px rgba(35, 24, 21, 0.09);
		cursor: pointer;
		font-size: 28px;
		font-weight: bold;
	}
</style>