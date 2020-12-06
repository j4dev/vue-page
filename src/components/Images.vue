<template>
  <div>
    <b-card-group deck>
      <div v-for="(photo,index) in photos.slice(0,5)" :key="index">
        <b-card
          v-bind:title="photo.title"
          v-bind:img-src="photo.thumbnailUrl"
          img-alt="Image"
          img-top
          tag="article"
          style="max-width: 20rem;"
          class="mb-2"
        >
          <b-card-text>
            {{photo.title}}
          </b-card-text>

          <b-button href="#" variant="primary">Go somewhere</b-button>
        </b-card>
      </div>
    </b-card-group>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";
import { Photo }  from "../models/photo.interface";

@Component
export default class Images extends Vue {
  @Prop() private msg!: string;

  photos: Array<Photo> = [];

  mounted() {
    this.getData();
  }
  async getData() {
    const response = await fetch("https://jsonplaceholder.typicode.com/photos");
    const json = await response.json();
    this.photos = json;
  }
}
</script>

<style scoped></style>
