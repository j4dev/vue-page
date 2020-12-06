<template>
  <div class="about">
    <Category/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Category from "../components/Category.vue";

@Component({
  components: {
    Category,
  }
})

export default class App extends Vue {}
</script>