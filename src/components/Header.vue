<template>
	<div id="header">
		<x-header slot="header" title="黄金甲">
			<img src="../assets/images/index/scan.png" slot="overwrite-left" @click="startRecognize()" />
			<img src="../assets/images/index/annouce.png" slot="right" />
		</x-header>
	</div>	
</template>

<script>
import { XHeader } from 'vux'

	
export default {
  name: 'vue-header',
  data () {
    return {
      title: '黄金甲'
    }
  },
  components: {
    XHeader
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less">
#header .vux-header{
	position: absolute;
	top: 0;
	width: 100%;
	background-color: #303030;
}
#header .vux-header-left,#header .vux-header-right{
	top: 8px;
	z-index: 100;
	img{
		max-width: 27px;			
	}
}
</style>
