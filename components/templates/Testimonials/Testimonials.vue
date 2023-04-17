<template>
  <div class="testimonial-wrap">
    <h3 v-if="title" class="display-2 text-center mb-4">
      Testimonials
    </h3>
    <p v-if="subtitle" class="body-1 text-center mb-4">
      Curabitur egestas consequat lorem, vel fermentum augue porta id.
    </p>
    <div class="carousel" v-if="loaded">
      <slick
        ref="slick"
        :options="slickOptions"
      >
        <div
          v-for="(item, index) in testiContent"
          :key="index"
          class="item"
        >
          <testi-card
            :text="item.text"
            :avatar="item.avatar"
            :name="item.name"
          />
        </div>
      </slick>
    </div>
  </div>
</template>

<style scoped lang="scss">
@import './testimonials-style';
</style>

<script>
import TestiCard from '../Cards/TestiCard'

export default {
  components: {
    Slick: () => import('vue-slick'),
    TestiCard
  },
  props: {
    title: {
      type: String,
      default: null
    },
    subtitle: {
      type: String,
      default: null
    },
    data: Array
  },
  data() {
    return {
      loaded: false,
      testiContent: this.data,
      slickOptions: {
        dots: true,
        arrows: false,
        slidesToShow: 3,
        infinite: true,
        autoplay: true,
        autoplaySpeed: 3000,
        responsive: [
          {
            breakpoint: 800,
            settings: {
              slidesToShow: 2,
              slidesToScroll: 1
            }
          },
          {
            breakpoint: 600,
            settings: {
              slidesToShow: 1,
              slidesToScroll: 1
            }
          }
        ]
      }
    }
  },
  mounted() {
    this.loaded = true
  },
  methods: {
    next() {
      this.$refs.slick.next()
    },

    prev() {
      this.$refs.slick.prev()
    },

    reInit() {
      this.$nextTick(() => {
        this.$refs.slick.reSlick()
      })
    }
  }
}
</script>
