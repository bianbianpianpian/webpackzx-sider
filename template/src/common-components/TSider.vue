<template>
	<div class="v-sider">
		<Menu mode="vertical" :theme="theme1" :active-name="activeName" :open-names="activeOpenName">
			<Submenu name="1" v-if="CONFIG_ROLE.STANDARDLOGISTICSCOST">
	            <template slot="title">
	            	<Icon type="md-apps"></Icon>
	                一级菜单1
	            </template>
			    <router-link to="/demo" class="navbar-brand" v-if="CONFIG_ROLE.STANDARDLOGISTICSCOST">
				    <MenuItem name="1-1">
				        <Icon type="md-link"></Icon>例1
				    </MenuItem>
			    </router-link>
	        </Submenu>
		</Menu>
	</div>
</template>
<script>
export default {
  name: 'TSider',
  data () {
    return {
      theme1: 'light',
      activeName: this.$route.name,
      activeOpenName: this.$route.name.split('-')[0] ? [this.$route.name.split('-')[0]] : [],
      CONFIG_ROLE: window.CONFIG_ROLE
    }
  },
  watch: {
    '$route' (to, from) {
      this.activeName = this.$route.name
      this.activeOpenName = this.$route.name.split('-')[0] ? [this.$route.name.split('-')[0]] : []
    }
  }
}
</script>