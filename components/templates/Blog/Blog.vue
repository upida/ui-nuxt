<template>
  <v-container>
    <scroll-wrap target="blog-list">
      <h3 v-if="title" class="display-2 text-center mb-4">
        Blog and News
      </h3>
      <p v-if="subtitle" class="body-1 text-center mb-4">
        Curabitur egestas consequat lorem, vel fermentum augue porta id.
      </p>
      <div
        id="blog-list"
        class="blog-wrap"
      >
        <v-row justify="center">
          <v-col md="9" cols="12">
            <v-row>
              <v-col
                v-for="(item, index) in blogData"
                :key="index"
                md="4"
                cols="12"
                class="px-4"
              >
                <blog-card
                  :title="item.title"
                  :desc="item.desc"
                  img="https://source.unsplash.com/random"
                />
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </div>
    </scroll-wrap>
  </v-container>
</template>

<style scoped lang="scss">
@import './blog-style';
</style>

<script>
import BlogCard from '../Cards/BlogCard'
import ScrollWrap from '../ScrollWrap'

export default {
  components: {
    BlogCard,
    ScrollWrap
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
      blogData: this.data
    }
  }
}
</script>
