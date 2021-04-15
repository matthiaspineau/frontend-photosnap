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
          <li class="navbar__li" @click="menuClose"><router-link to="/stories">stories</router-link></li>
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

    <!-- Footer -->
    <div class="wrapper__footer">
      <div class="container">

        <footer class="footer">  
          <!-- Logo -->
          <div class="footer__branding" @click="menuClose">  
            <img :src="require('@/assets/images/logo/logo_white.svg')" alt="logo site">
          </div>
          
          <!-- Socials -->
          <ul class="footer__socials__links">
            <li class="footer__socials__link">
              <img class="footer__socials__link--n" :src="require('@/assets/images/socials_icons/facebook.svg')" alt="logo socials">
              <img class="footer__socials__link--h" :src="require('@/assets/images/socials_icons/facebook_h.svg')" alt="logo socials">
            </li>
            <li class="footer__socials__link">
              <img class="footer__socials__link--n" :src="require('@/assets/images/socials_icons/youtube.svg')" alt="logo socials">
              <img class="footer__socials__link--h" :src="require('@/assets/images/socials_icons/youtube_h.svg')" alt="logo socials">
            </li>
            <li class="footer__socials__link">
              <img class="footer__socials__link--n" :src="require('@/assets/images/socials_icons/twitter.svg')" alt="logo socials">
              <img class="footer__socials__link--h" :src="require('@/assets/images/socials_icons/twitter_h.svg')" alt="logo socials">
            </li>
            <li class="footer__socials__link">
              <img class="footer__socials__link--n" :src="require('@/assets/images/socials_icons/pinterest.svg')" alt="logo socials">
              <img class="footer__socials__link--h" :src="require('@/assets/images/socials_icons/pinterest_h.svg')" alt="logo socials">
            </li>
            <li class="footer__socials__link">
              <img class="footer__socials__link--n" :src="require('@/assets/images/socials_icons/instagram.svg')" alt="logo socials">
              <img class="footer__socials__link--h" :src="require('@/assets/images/socials_icons/instagram_h.svg')" alt="logo socials">
            </li>
          </ul>

             <!-- links -->
          <ul class="footer__nav__links">
            <li class="footer__nav__link" @click="menuClose"><router-link to="/">home</router-link></li>
            <li class="footer__nav__link" @click="menuClose"><router-link to="/storie">storie</router-link></li>
            <li class="footer__nav__link" @click="menuClose"><router-link to="/features">features</router-link></li>
            <li class="footer__nav__link last" @click="menuClose"><router-link to="/pricing">pricing</router-link></li>
          </ul>

          <!-- Button -->
          <div class="footer__invite">
            <link-item :linkText="'Get an invite'" :onHeader="true"></link-item>
            <!-- <span>Get an invite</span>
            <svg class="svg__btn__arrow" viewBox="0 0 42 14" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M0 7H41.864" />
                    <path d="M35.4282 1L41.4282 7L35.4282 13" />
              </svg> -->
          </div>

          <!-- Copyright -->
          <h4 class="footer__copyright">Copyright 2019. All Rights Reserved</h4>

        </footer>

      </div>
    </div>

  </div>
</template>

<script>
import LinkItem from '@/components/LinkItem.vue'
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
  },
  components: {
    LinkItem   
  }
}
</script>

<style src="@/assets/scss/app.scss" lang="scss"></style>
