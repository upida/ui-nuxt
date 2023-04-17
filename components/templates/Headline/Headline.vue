<template>
<div>
  <div class="headline-more">
    <v-container>
      <u-animate-container>
        <scroll-wrap target="headline1">
          <v-row id="headline1">
            <v-col
              md="6"
              class="px-6"
              cols="12"
            >
              <div class="headline-item">
                <u-animate
                  name="fadeInLeft"
                  duration="0.6s"
                >
                  <h3 class="title-app display-2">{{title}}</h3>
                </u-animate>
                <u-animate
                  name="fadeInLeft"
                  delay="0.3s"
                  duration="0.6s"
                >
                  <p class="text">
                    {{subtitle}}
                  </p>
                </u-animate>
              </div>
            </v-col>
            <v-col
              md="6"
              class="px-6"
              cols="12"
            >
              <div class="headline-item">
                <u-animate
                  name="zoomIn"
                  delay="0.3s"
                  duration="0.6s"
                >
                  <div class="deco2" />
                </u-animate>
                <u-animate
                  name="fadeInRight"
                  delay="0.5s"
                  duration="0.6s"
                >
                  <div class="video-wrap">
                    <div class="video">
                      <youtube 
                        style="margin-top:-20%"
                        width="1080"
                        height="720"
                        video-id="sbef4EWb4js"
                        :playerVars="{ controls: 0 }"
                        @ready="onPlayerReady"
                        @ended="onPlayerReady"
                      />
                    </div>
                  </div>
                </u-animate>
              </div>
            </v-col>
          </v-row>
        </scroll-wrap>
      </u-animate-container>
    </v-container>
  </div>
</div>
</template>

<style scoped lang="scss">
@import './headline-styles';
</style>

<script>
import imgAPI from '~/static/images/imgAPI'

import ScrollWrap from '../ScrollWrap'

export default {
  components: {
    ScrollWrap
  },
  props: {
    title: String,
    subtitle: String
  },
  data() {
    return {
      imgAPI
    }
  },
  methods: {
    onPlayerReady(event) {
      event.mute();
      event.playVideo();
    }
  }
}
</script>
