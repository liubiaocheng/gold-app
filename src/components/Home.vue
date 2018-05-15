<template>
	<div id="home">		
		<view-box>
			<vue-header></vue-header>
			<swiper loop height="250px">
				<swiper-item v-for="(item, index) in swiperList">
					<img :src=item.thumb />
				</swiper-item>
			</swiper>
			<button-tab>
				<button-tab-item>关于黄金</button-tab-item>
        		<button-tab-item selected>掘金计划</button-tab-item>
        		<button-tab-item>黄金红包</button-tab-item>
			</button-tab>
			<marquee>
				<marquee-item>
					<div class="marqCon">实时金价：<span>278</span>元/克<x-button mini plain>活期金</x-button></div>
				</marquee-item>
				<marquee-item>
					<div class="marqCon">实时金价：<span>278</span>元/克<x-button mini plain>定期金</x-button></div>
				</marquee-item>
			</marquee>
			<div id="bcid">主体内容</div>	
			<vue-footer></vue-footer>
		</view-box>
	</div>
</template>

<script>
import { ViewBox,Swiper,SwiperItem,ButtonTab,ButtonTabItem,Marquee,MarqueeItem,XButton} from 'vux'
import Header from './Header'
import Footer from './Footer'


export default {
  name: 'home',
  components:{
  	ViewBox,
  	Swiper,
  	SwiperItem,
  	ButtonTab,
    ButtonTabItem,
    Marquee,
    MarqueeItem,
    XButton,
    'vue-header':Header,
    'vue-footer':Footer
  },
  data(){
  	return{
  		swiperList:[]
  	}
  },
  methods:{
  	startRecognize:function() {
  		alert("扫一扫");
//		scan = new plus.barcode.Barcode('bcid');
//		scan.onmarked = onmarked;
//      this.startScan 
	},
	startScan:function(){
    	scan.start();
	}  
  },
//showapi_appid=60345&showapi_test_draft=false&showapi_timestamp=20180511142205&type=34&showapi_sign=d2989abc0f83b90c3b8b7fce2baa0974
  created(){
  	var that = this;
  	this.$axios.get("http://route.showapi.com/819-1",
  		{params: 
  			{num:10,page:1,showapi_appid:60345,type:38,showapi_sign:'30F35806CC7ACC841CE22E58456708AB'}
  		}).then(function(res){
  			console.log(res);
  			var temp = res.data.showapi_res_body;
  			for(var i=0;i<5;i++){
  				that.swiperList.push(temp[i]);
  			}
			console.log(that.swiperList);
  		}).catch(function(res){
  			console.log(res);
  		})
  }
}
</script>

<style lang="less">
html, body {
  height: 100%;
  width: 100%;
  overflow-x: hidden;
}
#home{	
	height: 100%;
	.vux-slider{
		margin-top:46px;
		.vux-swiper-item{
			img{
				vertical-align: middle;				
			}
		}
	}	
	.vux-slider .vux-indicator-right > a > .vux-icon-dot.active{
		background-color:#d2a544;
	}
	/*#545454*/
	.vux-button-group{
		padding: 25px 12px 0 12px;
		height: 50px;
		background-color: #303030;	
		a.vux-button-tab-item-first:after,a.vux-button-tab-item-middle:after,a.vux-button-tab-item-last:after{
			border-color: #D2A544;
		}
	}
	.vux-button-group > a{
		color: #D2A544;
		background: #303030;
		&.vux-button-group-current{
			background: #fff;
		}	
	}
	.vux-marquee{
		margin: 10px auto;
		.vux-marquee-box li{
			height: 35px;
			line-height: 35px;
		}
	}
	.marqCon{
		zoom:1; 
		&:after{
			display:block;
			clear:both;
			content:"";
			visibility:hidden;
			height:0
		}
		padding-left: 15px;
		padding-right: 15px;
		span{
			color: #81010B;
		}
		button{
			float: right;
			border-color: #D2A544;
			color: #D2A544;
		}
	}
}
</style>