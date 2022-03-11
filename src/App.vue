<template>
  <header>
    <Navbar />
  </header>
  <main>
    <router-view />
  </main>
  <Modal id="blog-modal">
    <template #title>
      {{ activeBlog.title }}
    </template>
    <template #body>
      <img :src="activeBlog.imgUrl" alt="" class="img-fluid" />
    </template>

    <div class="d-flex w-100 justify-content-center"></div>
    <footer></footer>
  </Modal>
</template>


<script>
import { computed } from "vue";
import { AppState } from "./AppState";
import { useRouter } from "vue-router";
import { Modal } from "bootstrap";
export default {
  name: "App",
  setup() {
    const router = useRouter();
    return {
      goTo(page) {
        Modal.getOrCreateInstance(document.getElementById("blog-modal")).hide();
      },
      activeBlog: computed(() => AppState.activeBlog),
    };
  },
};
</script>
<style lang="scss">
@import "./assets/scss/main.scss";
</style>
