<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style lang="scss">
	/*每个页面公共css */
	:not(not){
			box-sizing: border-box;
		}
		page{
			background-color:#F8F8F8;
			color:$uni-text-color ;
			font-size:$uni-font-size-base ;
		}
	
</style>
