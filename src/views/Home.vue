<template>
  <div class="container mt-3">
    <Images/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Images from "../components/Images.vue";

@Component({
  components: {
    Images,
  }
})

export default class App extends Vue {}
</script>
