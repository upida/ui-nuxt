<template>
  <div>
    <section id="home" />
    <div class="main-wrap">
      <main-header :data="menu" />
      <main class="container-wrap">
        <section
          id="feature"
          class="space-top space-bottom"
        >
          <v-container>
            <feature />
          </v-container>
        </section>
        <section
          class="page-section"
        >
          <counter />
        </section>
        <section
          id="testimonials"
          class="space-top"
        >
          <testimonials :data="testimonials" />
        </section>
        <section
          id="pricing"
          class="space-top"
        >
          <pricing />
        </section>
        <section>
          <v-container>
            <animate-slider />
          </v-container>
        </section>
        <section
          id="blog"
          class="space-top space-bottom"
        >
          <blog :data="blog" />
        </section>
      </main>
      <hidden point="mdDown">
        <page-nav :data="menu" />
      </hidden>
      <main-footer />
    </div>
  </div>
</template>

<style scoped lang="scss">
@function section-margin($margin) {
  @return $margin * 15;
}
.main-wrap {
  position: relative;
  width: 100%;
  overflow: hidden;
}
.space-bottom {
  margin-bottom: section-margin($spacing1);
}
.space-top {
  padding-top: section-margin($spacing1);
}
.container-wrap {
  margin-top: $spacing15;
  & > section {
    position: relative;
  }
}
</style>

<script>
import imgAPI from '~/static/images/imgAPI'

import Header from '~/components/templates/Header'
import Hidden from '~/components/templates/Hidden'
import AnimateSlider from '~/components/templates/AnimateSlider'
import Feature from '~/components/templates/Feature'
import Counter from '~/components/templates/Counter'
import Testimonials from '~/components/templates/Testimonials'
import Pricing from '~/components/templates/Pricing'
import Blog from '~/components/templates/Blog'
import Subscribe from '~/components/templates/Subscribe'
import Footer from '~/components/templates/Footer'
import PageNav from '~/components/templates/PageNav'
import Notification from '~/components/templates/Notification'
import brand from '~/static/text/brand'

export default {
  components: {
    'main-header': Header,
    'animate-slider': AnimateSlider,
    Hidden,
    Feature,
    Counter,
    Testimonials,
    Pricing,
    Blog,
    Subscribe,
    PageNav,
    Notification,
    'main-footer': Footer,
  },
  head() {
    return {
      title: 'Home Page',
    }
  },
  data() {
    return {
      menu: ['feature', 'testimonials', 'pricing', 'blog'],
      headline: {},
      blog: [
        {
          text: 'Sed imperdiet enim ligula, vitae viverra justo porta vel.',
          avatar: imgAPI.avatar[10],
          name: 'Alex Tebalek - CTO La Lieur',
        },
        {
          text: 'Cras convallis lacus orci, tristique tincidunt magna consequat in. In vel pulvinar est, at euismod libero.',
          avatar: imgAPI.avatar[1],
          name: 'Jean Doe - VP Company',
        },
        {
          text: 'Cras convallis lacus orci, tristique tincidunt magna consequat in. In vel pulvinar est, at euismod libero.',
          avatar: imgAPI.avatar[2],
          name: 'Jena Doe - Graphic Designer',
        },
        {
          text: 'Sed imperdiet enim ligula, vitae viverra justo porta vel.',
          avatar: imgAPI.avatar[3],
          name: 'Jovelin - Senior Graphic Designer',
        },
        {
          text: 'Cras convallis lacus orci, tristique tincidunt magna consequat in. In vel pulvinar est, at euismod libero.',
          avatar: imgAPI.avatar[4],
          name: 'Jihan Doe - CEO Software House',
        },
        {
          text: 'Cras convallis lacus orci, tristique tincidunt magna consequat in. In vel pulvinar est, at euismod libero.',
          avatar: imgAPI.avatar[6],
          name: 'Jovelin - Senior Graphic Designer',
        },
        {
          text: 'Cras convallis lacus orci, tristique tincidunt magna consequat in. In vel pulvinar est, at euismod libero.',
          avatar: imgAPI.avatar[7],
          name: 'Jovelin - Senior Graphic Designer',
        },
      ],
      testimonials: [
        {
          text: 'Sed imperdiet enim ligula, vitae viverra justo porta vel.',
          avatar: imgAPI.avatar[10],
          name: 'Alex Tebalek - CTO La Lieur',
        },
        {
          text: 'Cras convallis lacus orci, tristique tincidunt magna consequat in. In vel pulvinar est, at euismod libero.',
          avatar: imgAPI.avatar[1],
          name: 'Jean Doe - VP Company',
        },
        {
          text: 'Cras convallis lacus orci, tristique tincidunt magna consequat in. In vel pulvinar est, at euismod libero.',
          avatar: imgAPI.avatar[2],
          name: 'Jena Doe - Graphic Designer',
        },
        {
          text: 'Sed imperdiet enim ligula, vitae viverra justo porta vel.',
          avatar: imgAPI.avatar[3],
          name: 'Jovelin - Senior Graphic Designer',
        },
        {
          text: 'Cras convallis lacus orci, tristique tincidunt magna consequat in. In vel pulvinar est, at euismod libero.',
          avatar: imgAPI.avatar[4],
          name: 'Jihan Doe - CEO Software House',
        },
        {
          text: 'Cras convallis lacus orci, tristique tincidunt magna consequat in. In vel pulvinar est, at euismod libero.',
          avatar: imgAPI.avatar[6],
          name: 'Jovelin - Senior Graphic Designer',
        },
        {
          text: 'Cras convallis lacus orci, tristique tincidunt magna consequat in. In vel pulvinar est, at euismod libero.',
          avatar: imgAPI.avatar[7],
          name: 'Jovelin - Senior Graphic Designer',
        },
      ],
    }
  },
}
</script>
