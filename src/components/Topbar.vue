<template>
  <header class="header" v-once>
    <div class="header__branding">
    Gradientful
        </div>
      </a>
    </div>

    <ul class="social header__social">
      <li>
        <a
          href="#" class="button button--twitter" @click.prevent="shareOnTwitter()">
          <Twitter class="button__icon" />
          <span>Share on Twitter</span>
        </a>
      </li>
      <li class="ml10">
        <a href="#" class="button button--facebook" @click.prevent="shareOnFacebook()">
          <Facebook class="button__icon" />
          <span>Share on Facebook</span>
        </a>
      </li>
      <li class="ml10">
        <a href="https://github.com/S-codes14/gradientful" target="_blank" @click="goToGithub()">
          <Github class="header__github" />
        </a>
      </li>
    </ul>
  </header>
</template>

<script>
import Plus from '../assets/plus.svg';
import Arrow from '../assets/arrow.svg';
import Logo from '../assets/logo.svg';
import Facebook from '../assets/facebook.svg';
import Twitter from '../assets/twitter.svg';
import Github from '../assets/github.svg';
import Skillshare from '../assets/skillshare.svg';

export default {
  name: 'topbar',
  components: {
    Arrow,
    Plus,
    Logo,
    Facebook,
    Twitter,
    Github,
    Skillshare,
  },
  methods: {
    goToSkillshare() {
      this.$ga.event('sponsor', 'click', 'Skillshare');
    },
    goToGithub() {
      this.$ga.event('social', 'click', 'github');
    },
    shareOnTwitter() {
      this.$ga.social('twitter', 'share', 'http://gradientful.netlify.app/');
      window.open(
        'http://twitter.com/share?url=https://gradientful.netlify.app&amp;text=Beautiful%20color%20gradients%20for%20designers%20and%20developers&amp;via=Sibongu14624275',
        'twitter-share',
        'width=700,height=300',
      );
    },
    shareOnFacebook() {
      this.$ga.social('facebook', 'share', 'http://gradientful.netlify.app/');
      window.open(
        'http://www.facebook.com/sharer.php?u=https://gradientful.netlify.app',
        'facebook-share',
        'width=700,height=400',
      );
    },
  },
};
</script>
