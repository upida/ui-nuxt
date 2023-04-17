<template>
  <div>
    <section id="home" />
    <div class="main-wrap">
      <main-header :data="menu" />
      <main class="container-wrap">
        <parallax-main />
        <section
          id="headline"
          class="space-top"
        >
          <headline
            :title="brand.starter.projectName"
            :subtitle="brand.starter.desc"
            :data="headline"
          />
        </section>
        <section
          id="screenshots"
          class="space-top"
        >
          <screenshots
            :data="screenshots" 
          />
        </section>
        <section
          id="features"
          class="space-top"
        >
          <features
            :data="features" 
          />
        </section>
        <section
          id="testimonials"
          class="space-top space-bottom"
        >
          <testimonials
            title="Testimonials"
            subtitle="Curabitur egestas consequat lorem, vel fermentum augue porta id." 
            :data="testimonials"
          />
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
import brand from '~/static/text/brand'

import Header from '~/components/templates/Header'
import ParallaxMain from '~/components/templates/Parallax/Main'
import Hidden from '~/components/templates/Hidden'
import Footer from '~/components/templates/Footer'
import PageNav from '~/components/templates/PageNav'

import Headline from '~/components/home/Headline'
import Screenshots from '~/components/home/Screenshots'
import Features from '~/components/home/Features'
import Testimonials from '~/components/home/Testimonials'

export default {
  head() {
    return {
      title: 'Home',
    }
  },
  components: {
    'main-header': Header,
    Hidden,
    ParallaxMain,
    Headline,
    Screenshots,
    Features,
    Testimonials,
    PageNav,
    'main-footer': Footer,
  },
  data() {
    return {
      brand: brand,
      menu: ['home', 'screenshots', 'features', 'testimonials'],
      headline: {},
      screenshots: [
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
      features: [
        {
          title: 'Feature 1',
          desc: 'This is a media card. You can use this section to describe the content.',
        },
        {
          title: 'Feature 2',
          desc: 'This is a media card. You can use this section to describe the content.',
        },
        {
          title: 'Feature 3',
          desc: 'This is a media card. You can use this section to describe the content.',
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
  mounted() {},
}
</script>
