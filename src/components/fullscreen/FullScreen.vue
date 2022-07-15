<template>
  <div class="full-screen">
    <Swiper
      :loop="true"
      :speed="800"
      :pagination="true"
      :navigation="true"
      :modules="modules"
      class="full-screen__carousel"
    >
      <SwiperSlide v-for="slide in 3" :key="slide" class="full-screen__slide">
        <div class="full-screen__content">
          <h1 class="full-screen__title">Capsule Collection</h1>
        </div>
      </SwiperSlide>
    </Swiper>
  </div>
</template>

<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";

import { Pagination, Navigation } from "swiper";
import "swiper/css/pagination";
import "swiper/css/navigation";

export default {
  components: {
    Swiper,
    SwiperSlide,
  },

  setup() {
    return {
      modules: [Pagination, Navigation],
    };
  },
};
</script>

<style lang="scss" scoped>
.full-screen {
  width: 100%;
  min-height: 100vh;
}
.full-screen__carousel {
  height: 100vh;
}
.full-screen__slide {
  background: url("../../assets/img/bg.jpg") center / cover no-repeat;
}

.full-screen__content {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
}

.full-screen__title {
  color: #fff;
}
</style>
