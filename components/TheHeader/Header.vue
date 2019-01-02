<template>
  <nav class="navbar has-shadow is-dark" role="navigation" aria-label="main navigation">
    <div class="container">
      <div class="navbar-brand">
				<a class="navbar-item" href="/">
					<img src="~assets/images/logo_blu.png" alt="BLUITDEV">
					<span> &nbsp; BlogPost</span>
				</a>
				<a role="button" class="navbar-burger burger" :class="{'is-active': menuActive}" v-on:click="toggleNavbar()" aria-label="menu" aria-expanded="false" data-target="navbarMenu">
					<span aria-hidden="true"></span>
					<span aria-hidden="true"></span>
					<span aria-hidden="true"></span>
				</a>
      </div>
      <div id="navbarMenu" class="navbar-menu" v-bind:class="{ 'is-active': menuActive }">
        <div class="navbar-end">
          <nuxt-link to="/about" class="navbar-item">
              <span class="icon"><font-awesome-icon icon="info-circle"/></span>&nbsp;Giới thiệu
          </nuxt-link>
          <nuxt-link to="/" class="navbar-item" title="Tất cả bài viết">
              <span class="icon"><font-awesome-icon icon="book"/></span>&nbsp;Tất cả
          </nuxt-link>
          <a class="navbar-item">
              <span class="icon"><font-awesome-icon icon="book-reader"/></span>&nbsp;Kiến thức
          </a>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
	data() {
		return {
			menuActive: false
		}
	},
	methods: {
		toggleNavbar() {
			this.menuActive = !this.menuActive;
		}
	}
}
</script>
