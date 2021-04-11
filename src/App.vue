<template>
  <div id="app">

    <!-- Navbar -->
    <nav id="nav" class="container">
      <div id="navbar" class="navbar" :class="{'active' : menuIsActive}">
        <!-- Logo site -->
        <div class="navbar__branding" @click="menuClose">
          <router-link to="/">
            <img :src="require('@/assets/images/logo/logo_black.svg')" alt="logo site">
          </router-link>
        </div>

        <!-- Links -->
        <ul class="navbar__ul">
          <li class="navbar__li" @click="menuClose"><router-link to="/storie">storie</router-link></li>
          <li class="navbar__li" @click="menuClose"><router-link to="/features">features</router-link></li>
          <li class="navbar__li" @click="menuClose"><router-link to="/pricing">pricing</router-link></li>
          <li class="navbar__li navbar__li__last" @click="menuClose"><span>Get an invite</span></li>
        </ul>
        <div class="get__invite" @click="menuClose"><span>Get an invite</span></div>
        <!-- Button menu -->
        <div class="navbar__action">
          <span class="navbar__action__open"
          @click="menuOpen">
            <img :src="require('@/assets/images/open_icon.svg')" alt="logo site">
            </span>
          <span class="navbar__action__close"
          @click="menuOpen">
            <img :src="require('@/assets/images/close_icon.svg')" alt="logo site">
          </span>
        </div>
      </div>
    </nav>

    <!-- Divider -->
    <div class="divider" :class="{'active' : menuIsActive}" @click="menuClose"></div>

    <!-- View -->
    <router-view/>
  </div>
</template>

<script>
export default {
  data() {
    return {
      menuIsActive: false
    }
  },
  methods: {
    menuOpen() {
      this.menuIsActive = !this.menuIsActive
    },
    menuClose() {
      this.menuIsActive = false
    }
  }
}
</script>

<style src="@/assets/scss/app.scss" lang="scss"></style>
