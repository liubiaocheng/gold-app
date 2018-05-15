<template>
	<div id="footer">
		<tabbar slot="bottom">
			<tabbar-item selected>
				<img src="../assets/images/index/icon_home.png" slot="icon"/>
				<img src="../assets/images/index/icon_home_active.png" slot="icon-active" />
				<span slot="label">首页</span>	
			</tabbar-item>
			<tabbar-item>
				<img src="../assets/images/index/icon_caculate.png" slot="icon"/>
				<img src="../assets/images/index/icon_caculate_active.png" slot="icon-active" />
				<span slot="label">计算器</span>
			</tabbar-item>
			<tabbar-item>
				<img src="../assets/images/index/icon_mine.png" slot="icon" />
				<img src="../assets/images/index/icon_mine_active.png" slot="icon-active" />
				<span slot="label">我的</span>
			</tabbar-item>
			<tabbar-item>
				<img src="../assets/images/index/icon_search.png" slot="icon" />
				<img src="../assets/images/index/icon_search_active.png" slot="icon-active" />
				<span slot="label">搜索</span>
			</tabbar-item>
			<tabbar-item>
				<img src="../assets/images/index/icon_share.png" slot="icon" />
				<img src="../assets/images/index/icon_share_active.png" slot="icon-active" />
				<span slot="label">分享</span>
			</tabbar-item>
		</tabbar>
	</div>	
</template>

<script>
import { Tabbar,TabbarItem} from 'vux'
	
export default {
  name: 'vue-footer',
  data () {
    return {
      
    }
  },
  components: {
    Tabbar,
    TabbarItem
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less">
#footer .weui-tabbar{
	background-color: #303030;
	.weui-tabbar__item.weui-bar__item_on .weui-tabbar__label{
		color: #D2A544;
	}
}
</style>
