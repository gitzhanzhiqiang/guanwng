 <template>  
  <div class="footer">
		<div class="footthe">
			<h2>WE'RE HERE</h2>
			<div class="footthe_left">
				<ul>
					<li>Email：12345678@qq.com</li>
					<li>Tel:12345678</li>
				</ul>
				<p>ADDRESS: addressaddressaddressaddressaddres.saddressaddress</p>
			</div>
			<div class="footthe_right">
				<ul>
					<li><img :src="fff"/></li>
					<li><img :src="niao"/></li>
				</ul>
			</div>
		</div>
		<div class="record">
			© 2018 Gold Ore. All Rights Reserved
		</div>
  </div>
</template>

<script>
export default {
  data() {
  	 var footb = require("@res/imgs/footbei.png");
  	 var niaod = require("@res/imgs/niao.png")
  	 var fffd = require("@res/imgs/fff.png")
      return {
      	niao: require("@res/imgd/niao.png"),
      	fff: require("@res/imgd/fff.png"),
      	footb: {
                backgroundImage: "url(" + footb + ")",
            },
            niaod: {
                backgroundImage: "url(" + niaod + ")",
            },
             fffd: {
                backgroundImage: "url(" + fffd + ")",
            },
      }
  },
  computed: {

  },
  created() {
      console.log(this.data);
      this.url = [{ url: this.img1 }, { url: this.img1 }];
  },
  mounted() {
  },
  methods: {
  },
  filters: {
  }
}
</script>
<style type="less" scoped>
  .footer {
    height:232px;
    width: 100%;
    margin: auto;
    background: #3A62D2;
}
.footthe{
    	width: 1100px;
    	height: 169px;
    	margin: 0 auto;
    }
   .footthe h2{
    		width: 100%;
    		font-family:Tahoma;
font-weight:bold;
font-style:italic;
color:rgba(255,255,255,1);
line-height:36px;
			float: left;
			margin-top: 26px;
			margin-bottom: 20px;
    	}
    .footthe_left{
    	overflow: hidden;
    	float: left;
    }
  .footthe_left ul{
  	overflow: hidden;
  }
   .footthe_left ul li{
   	width: 199px;
   	height: 39px;
   	border: 1px solid white;
   	float: left;
   	line-height: 39px;
   	color: white;
   	text-align: center;
   }
   .footthe_left ul li:first-child{
   		background: white;
   		width: 300px;
   		font-size:14px;
		font-family:MicrosoftYaHei;
		font-weight:400;
		color: #010101;
   }
 .footthe_left p{
 	font-size:14px;
font-family:MicrosoftYaHei;
font-weight:400;
color:rgba(255,255,255,1);
margin-top: 25px;
 }

   
   .footthe_right{
    	overflow: hidden;
    	float: right;
    }
   .footthe_right ul li{
   	float: left;
   	width: 60px;
   	height: 60px;
   	margin-left: 30px;
   }
  
   .record{
   	width: 100%;
   	height: 63px;
   	 background: #3A62D2;
   	line-height: 63px;
   	text-align: center;
   font-size:14px;
font-family:MicrosoftYaHei;
font-weight:400;
color:rgba(255,255,255,1);
opacity:0.6;
   }
</style>
