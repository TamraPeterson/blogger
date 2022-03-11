<template>
  <div
    class="blogs"
    data-bs-toggle="modal"
    data-bs-target="#blog-modal"
    @click="setActive"
  >
    <div class="text-center">
      <h5>{{ blog.title }}</h5>
      <img
        :src="blog.imgUrl"
        alt=""
        class="img-fluid image p-2 shadow selectable"
      />
    </div>
  </div>
</template>


<script>
import { logger } from "../utils/Logger";
import Pop from "../utils/Pop";
import { blogsService } from "../services/BlogsService";
import { AppState } from "../AppState";
import { computed } from "@vue/reactivity";
import { onMounted } from "@vue/runtime-core";
export default {
  props: {
    blog: {
      type: Object,
      required: true,
    },
  },
  setup(props) {
    onMounted(async () => {
      try {
      } catch (error) {}
    });
    return {
      setActive() {
        blogsService.setActive(props.blog);
      },
    };
  },
};
</script>


<style lang="scss" scoped>
.image {
  height: 300px;
  width: 300px;
}
</style>