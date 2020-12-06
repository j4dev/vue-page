<template>
  <div class="container mt-3">
    <div v-for="(categ,index) in category" :key="index">
      <h1>Usted esta en la categoria: {{categ.name}}</h1>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";
import { CategoryI }  from "../models/category.interface";

@Component
export default class Category extends Vue {
  @Prop() private msg!: string;

  category: Array<CategoryI> = [];

  mounted() {
    this.getData();
  }
  async getData() {
    const response = await fetch("https://jsonfy.com/categories/"+this.$route.params.id);
    const json = await response.json();
    this.category = json;
    console.log(this.category);
    
  }
}
</script>

<style scoped></style>
