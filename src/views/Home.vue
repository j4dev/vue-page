<template>
  <div class="container mt-3">
    <b-card-group deck>
    <div v-for="(photo,index) in photos.slice(0, 5)" :key="index">
      <b-card
        title="Card Title"
        v-bind:img-src="photo.url"
        img-alt="Image"
        img-top
        tag="article"
        style="max-width: 20rem;"
        class="mb-2"
      >
        <b-card-text>
          Some quick example text to build on the card title and make up the
          bulk of the card's content.
        </b-card-text>

        <b-button href="#" variant="primary">Go somewhere</b-button>
      </b-card>
    </div>
    </b-card-group>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class NavBar extends Vue {
  @Prop() private msg!: string;

  photos = [];

  mounted() {
    this.getPhotos();
  }
  async getPhotos() {
    const response = await fetch("https://jsonplaceholder.typicode.com/photos");
    const json = await response.json();
    this.photos = json;
  }
}
</script>
