<template>
    <div class="bodyCon" id="uptop">
       <div class="bodyCon_z">
       	 <!-- logo -->
        <div class="logo" style="cursor: pointer;">
            <div class="logoImg" @click="activeChange(4);$router.push('/sunfin/index');aboutChange();servChange();">
                <img :src="loginUrl" alt="" width="100%" height="100%">
            </div>
        </div>
        <!-- 菜单导航 -->
        <div class="header">
            <ul class="menu">
            	<em class="ema" v-on:mouseenter="dataDetails('servicesUpDown',1)" v-on:mouseleave="hiddenDetail('servicesUpDown')"></em>
            	<em class="emb" v-on:mouseenter="dataDetails('aboutUpDown')" v-on:mouseleave="hiddenDetail('aboutUpDown')"></em>
            	 <li @click="activeChange(4);aboutChange();servChange();active4 = true;$router.push('/sunfin/index')" :class="{'active': active4 && !$store.getters.nav}">
                    <span>Home</span>
                </li>
                <li @click="activeChange(1);aboutChange();servChange();aboutUpDown = false;active1 = true;$router.push('/sunfin/services')" :class="{'active': active1 && !$store.getters.nav}" v-on:mouseenter="dataDetails('servicesUpDown')" v-on:mouseleave="hiddenDetail('servicesUpDown')">
                    <span>SERVICES
                        <i v-if="!servicesUpDown" @click="servicesUpDown = !servicesUpDown;" class="el-icon-arrow-down"></i>
                        <i v-if="servicesUpDown" @click="servicesUpDown = !servicesUpDown;" class="el-icon-arrow-up"></i>
                    </span>
                </li>
                <li @click="activeChange(2);aboutChange();servChange();servicesUpDown = false;active2 = true;$router.push('/sunfin/aboutUs')" :class="{'active': active2 && !$store.getters.nav}" v-on:mouseenter="dataDetails('aboutUpDown')" v-on:mouseleave="hiddenDetail('aboutUpDown')">
                    <span>ABOUT US
                        <i v-if="!aboutUpDown" @click="aboutUpDown = !aboutUpDown;" class="el-icon-arrow-down"></i>
                        <i v-if="aboutUpDown" @click="aboutUpDown = !aboutUpDown;" class="el-icon-arrow-up"></i>
                    </span>
                </li>
                <li @click="activeChange(3);aboutChange();servChange();active3 = true;$router.push('/sunfin/news')" :class="{'active': active3 && !$store.getters.nav}">
                    <span>NEWS</span>
                </li>
                <li @click="activeChange(3);aboutChange();servChange();active3 = true;$router.push('/sunfin/news')" :class="{'active': active3 && !$store.getters.nav}">
                    <span>Contact Us</span>
                </li>
                <li style="margin-left: 90px;" @click="activeChange(3);aboutChange();servChange();active3 = true;$router.push('/sunfin/index')" :class="{'active': active3 && !$store.getters.nav}">
                    <span>Sign In</span>
                </li>
            </ul>
            
            <!-- 二级菜单隐藏 -->
            <div class="aboutSecondMenu" v-if="aboutUpDown" v-on:mouseenter="dataDetails('aboutUpDown')" v-on:mouseleave="hiddenDetail('aboutUpDown')">
                <div class="menuItem" @click="servChange();$router.push('/sunfin/aboutUs');activeChange(2);active2 = true;aboutChange(1);about1 = true" :class="{'actives': about1}" style="margin-top: 15px;">
                    <li>What is Gold Ore?</li>
                </div>
                <div class="menuItem" @click="servChange();$router.push('/sunfin/advantages');activeChange(2);active2 = true;aboutChange(2);about2 = true" :class="{'actives': about2}">
                    <li>Project background</li>
                </div>
                <div class="menuItem" @click="servChange();$router.push('/sunfin/mission');activeChange(2);active2 = true;aboutChange(3);about3 = true" :class="{'actives': about3}">
                    <li>Why you choose Gold Ore ?</li>
                </div>
                 <div class="menuItem menuItem2" @click="servChange();$router.push('/sunfin/company');activeChange(2);active4 = true;aboutChange(4);about4 = true" :class="{'actives': about4}" style="margin-bottom: 15px;">
                    <li>company</li>
                </div>
            </div>
            <div class="serviceSecondMenu" v-if="servicesUpDown" v-on:mouseenter="dataDetails('servicesUpDown')" v-on:mouseleave="hiddenDetail('servicesUpDown')">
               <div class="menuItem" @click="$router.push('/sunfin/services');activeChange(1);active1 = true;servChange(1);serv1 = true" :class="{'active': serv1 && !$store.getters.nav}" style="margin-top: 15px;">
                    Award planning for developers
                </div>
                <div class="menuItem" @click="aboutChange();$router.push('/sunfin/trustservice');activeChange(1);active1 = true;servChange(2);serv2 = true" :class="{'active': serv2 && !$store.getters.nav}">
                    Partner Planning
                </div>
                <div class="menuItem" @click="aboutChange();$router.push('/sunfin/insuranceService');activeChange(1);active1 = true;servChange(3);serv3 = true" :class="{'active': serv3 && !$store.getters.nav}">
                    Block Chain Ivy Academy Planning
                </div>
                <div class="menuItem" @click="aboutChange();$router.push('/sunfin/enterpriseFinancing');activeChange(1);active1 = true;servChange(4);serv4 = true" :class="{'active': serv4 && !$store.getters.nav}">
                    Overseas Study Tour Planning
                </div>
               <!-- <div class="menuItem menuItem2" @click="aboutChange();$router.push('/sunfin/situation');activeChange(1);active1 = true;servChange(5);serv5 = true" :class="{'active': serv5 && !$store.getters.nav}" style="margin-bottom: 15px;">
                   WIN-WIN Planning
                </div>-->
            </div>
        </div>
       </div>
    </div>
</template>

<script>

import ajax from '@utils/config';
export default {
    data() {
    	 var guoqi = require("@res/imgs/guoqi.png");
        return {
            loginUrl: require("@res/imgd/logo.png"),
          	guoqi: {
                backgroundImage: "url(" + guoqi + ")",
            },
            bodyCona:false,
            active0: false,
            active1: false,
            active2: false,
            active3: false,
            active4: false,
            active5: false,
            
            serv1: false,
            serv2: false,
            serv3: false,
            serv4: false,
            serv5: false,
            
            about1: false,
            about2: false,
            about3: false,
            
            aboutUpDown: false,
            servicesUpDown: false,
            data: [
                { path: '/sunfin/index', name: 'HOME' },
                {
                    path: '/sunfin/services', name: 'SERVICES', children: [
                        {
                            path: '/sunfin/services', name: 'SERVICES', children: [
                                { path: '/sunfin/services', name: 'SERVICES', }
                            ]
                        }
                    ]
                },
                { path: '/sunfin/aboutUs', name: 'ABOUT US' },
                { path: '/sunfin/news', name: 'NEWS' },
                { path: '/sunfin/contactUs', name: 'CONTACT US' }
            ],
            activeIndex: '0'
        }
    },
    created() {
        this.gun()
    },
    computed: {
        //     ...mapGetters([
        //       'headerRouter'
        //   ])
    },
    mounted() {
        console.log(this.$store.getters)
    },
    methods: {
    	gun() {
				window.onscroll = function(){ 
			     var t = document.documentElement.scrollTop || document.body.scrollTop;  //获取距离页面顶部的距离
			     var uptop = document.getElementById( "uptop" ); //获取div元素
			     if( t >= 300 ) { //当距离顶部超过300px时
			     	uptop.style.width="100%";
			     	uptop.style.top="0";
			     } else { //如果距离顶部小于300px
			     	uptop.style.width="";
			     	uptop.style.top="";
			     } 
			} 

			},
    	dataDetails(num){
    		if(num == 'servicesUpDown'){
    			this.servicesUpDown= true
    		}else if(num == 'aboutUpDown'){
    			this.aboutUpDown= true
    		}
    	},
    	hiddenDetail(num){
    		if(num == 'servicesUpDown'){
    			this.servicesUpDown= false
    		}else if(num == 'aboutUpDown'){
    			this.aboutUpDown= false
    		}
    	},
        handleSelect(key, keyPath) {
            //console.log(key, keyPath);
        },
        activeChange(index) {
        	console.log(index)
            this.active0 = false;
            this.active1 = false;
            this.active2 = false;
            this.active3 = false;
            this.active4 = false;
            this.active5 = false;
            this.setStore()
        },
        servChange(index) {
            this.serv1 = false;
            this.serv2 = false;
            this.serv3 = false;
            this.serv4 = false;
            this.serv5 = false;
            this.serv6 = false;
            this.setStore()
        },
        aboutChange(index) {
            this.about1 = false;
            this.about2 = false;
            this.about3 = false;
            this.setStore()
        },
        setStore () {
             this.$store.dispatch('NAVSET', { nav: null});
        },
        getAddRouter() {
            this.listInfo = this.$store.getters.allRouter[Cookies.get('submenuIndex')].children;
        },
        //鼠标移入
        menter(index) {
            // this.listInfo[index].img = this.listInfo[index].imgHover;
        },
        //
        goFirstRouter(item) {
            if (item.children.length === 0) {
                this.$router.push(item.path);
            }
        },
        //鼠标滑出
        mleave(index) {
            // this.listInfo[index].img = this.listInfo[index].img1;
        },
        handleOpen(key, keyPath) {
            //console.log(key, keyPath);
        },
        handleClose(key, keyPath) {
            //console.log(key, keyPath);
        },
        go_url(children) {
            if (children.children.length == 0) {
                this.$router.push(children.path);
            }
        }
    }
}
</script>
<style lang="less" scoped>
.bodyCon {
    width:1400px;
	height:80px;
    background:rgba(255,255,255,0.8);
    box-shadow:0px 0px 13px rgba(35,24,21,0.1);
      position: fixed;
    z-index: 999;
    top: 25px;
    left: 50%;
    transform: translateX(-50%);
    border-radius:8px;
    .bodyCon_z{
    	width: 1100px;
    	height:80px;
    	margin: 0 auto;
    }
    .logo {
        float: left;
        width:149px;
		height:50px;
        margin-top: 13px;
    }
    .header {
        float: left;
        height: 100%;
        width: 821px;
        float: right;
        line-height: 100px;
        position: relative;
        .menu{
        	float: right;	
            height: 100%;
            line-height: 103px;
            position: relative;
            &>em{
            	 width: 0;
	            height: 0;
	            border-bottom: 10px solid #ffffff;
	            border-left: 10px solid transparent;
	            border-right: 10px solid transparent;
	            position: absolute;
	            bottom: 17px;
	            z-index: 999;
            }
            &>em.ema{
            	left: 45px;
            }
             &>em.emb{
            	left: 260px;
            }
            &>li {
            	cursor: pointer;
                float: left;
                height:80px;
                margin-left: 30px;
                font-size:14px;
                font-family:MicrosoftYaHei-Bold;
                font-weight:600;
                color:#333333;
                line-height:80px;
                text-align: center;
                &>span {
                    padding: 11px 15px;
                    width: 120px;
                    color:#333333;
                }
            }
            &>li.active {
                color:rgba(102,102,102,1);
                height:48px;
                text-align: center;
                &>span {
                    width: 120px;
                    font-family:MicrosoftYaHei-Bold;
                    font-weight:600;
                    border-bottom: 1px solid #343FA7;
                }
            }
        }
        .menus{
        	float: right;
            height: 100%;
             line-height: 100px;
            &>p{
            	float: left;
                height:48px;
                font-size:14px;
                font-family:MicrosoftYaHei-Bold;
                font-weight:600;
                color:#333333;
                line-height:48px;
                text-align: center;
                margin-top: 34px;
                &>.flag{
                	display: inline-block;
                	width: 18px;
                	height: 12px;
                	background-size:100% 100% ;
                	margin-right: 14px;
                }
            }
            &>span{
            	float: left;
            	width: 80px;
            	height: 26px;
            	display: inline-block;
            	font-size:14px;
				font-family:MicrosoftYaHei-Bold;
				font-weight:bold;
				color:rgba(72,134,239,1);
				 line-height: 28px;
				 text-align: center;
				 border: 1px solid #4886EF;
				 border-radius:11px;
				 margin-top: 44px;
				 margin-left: 26px;
				 margin-right: 26px;
				 cursor: pointer;
            }
        }
        .aboutSecondMenu {
            position: absolute;
            left: 330px;
            top:83px;
            width:245px;
            background:rgba(255,255,255,1);
            border-radius:8px;
            box-shadow:0px 0px 6px rgba(0,0,0,0.15);
            z-index: 99;
            .menuItem {
                width: 210px;
                height: 25%;
                border-bottom: 1px solid rgba(230,230,230,1);
                margin-left: 15px;
                font-size:16px;
                font-family:MS Sans Serif;
                font-weight:400;
                color:rgba(102,102,102,1);
                line-height:35px;
                cursor:pointer;
                text-align: justify;
            }
            .menuItem2 {
                border: none;
                cursor:pointer
            }
        }
        .serviceSecondMenu {
            position: absolute;
            left: 100px;
            top:83px;
            width:315px;
            overflow: hidden;
            background:rgba(255,255,255,1);
            border-radius:8px;
            box-shadow:0px 0px 5px rgba(0,0,0,0.15);
            z-index: 99;
            .menuItem {
                width: 265px;
                border-bottom: 1px solid rgba(230,230,230,1);
                margin-left: 25px;
                font-size:16px;
                font-family:MS Sans Serif;
                font-weight:400;
                color:rgba(102,102,102,1);
                line-height:38px;
                cursor:pointer
            }
            .menuItem2 {
                border: none;
                cursor:pointer
            }
        }
    }

}

.bodyCon .header .menus span a{
	 display: inline-block;
	 color:#4886ef;
	  opacity: 0;
	  transform: translate(-150px, 0) scale(.3);
	  animation: leftRight .5s forwards;
}

.bodyCon .header .menus span a:nth-of-type(2) {
  animation-delay: .05s;
}

.bodyCon .header .menus span a:nth-of-type(3) {
  animation-delay: .1s;
}

.bodyCon .header .menus span a:nth-of-type(4) {
  animation-delay: .15s;
}

.bodyCon .header .menus span a:nth-of-type(5) {
  animation-delay: .2s;
}

.bodyCon .header .menus span a:nth-of-type(6) {
  animation-delay: .25s;
}

.bodyCon .header .menus span a:nth-of-type(7) {
  animation-delay: .3s;
}

.bodyCon .header .menus span a:nth-of-type(8) {
  animation-delay: .35s;
}

.bodyCon .header .menus span a:nth-of-type(9) {
  animation-delay: .4s;
}

.bodyCon .header .menus span a:nth-of-type(10) {
  animation-delay: .45s;
}

.bodyCon .header .menus span a:nth-of-type(11) {
  animation-delay: .5s;
}

.bodyCon .header .menus span a:nth-of-type(12) {
  animation-delay: .55s;
}

.bodyCon .header .menus span a:nth-of-type(13) {
  animation-delay: .6s;
}

.bodyCon .header .menus span a:nth-of-type(14) {
  animation-delay: .65s;
}


@keyframes leftRight {
  40% {
    transform: translate(50px, 0) scale(.7);
    opacity: 1;
    color: #4886ef;
  }
  60% {
    color: #4886ef;
  }
  80% {
    transform: translate(0) scale(2);
    opacity: 0;
  }
  100% {
    transform: translate(0) scale(1);
    opacity: 1;
  }
}

.bodyCon .header .menus span:hover a{
	display: inline-block;
	  color: #4886ef;
  opacity: 0;
  transform: translate(-150px, -50px) rotate(-180deg) scale(3);
  animation: revolveScale .4s forwards;
}
.bodyCon .header .menus span:hover{
	    border: 1px dashed #4886EF;
}
@keyframes revolveScale {
  60% {
    transform: translate(20px, 20px) rotate(30deg) scale(.3);
  }
  100% {
    transform: translate(0) rotate(0) scale(1);
    opacity: 1;
  }
}


.menu li:hover span{
	border-bottom: 1px solid #343FA7;
}
.serviceSecondMenu .active{
	color:#4886ef !important;
	font-weight: 600 !important;
}
.aboutSecondMenu .actives li{
	color:#4886ef !important;
	font-weight: 600 !important;
}
.serviceSecondMenu .menuItem:hover{
	color:#4886ef !important;
	font-weight: 600 !important;
	
}
.aboutSecondMenu .menuItem li:hover{
	color:#4886ef !important;
	font-weight: 600 !important;
}
</style>

