<template>
  <div>
    <b-navbar toggleable="lg" type="dark" variant="info">
      <b-navbar-brand>
        <a href="https://github.com/j4dev" target="_blank">
          <img
            src="../../assets/LogoGithub.png"
            alt="j4dev"
            width="75px"
            height="20px"
          />
        </a>
      </b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item to="/">Inicio</b-nav-item>
          <b-nav-item-dropdown text="Categorias" right>
            
            <div v-for="(category,index) in categories" :key="index">
              <b-dropdown-item v-bind:to="'/category/'+category.id">{{category.name}}</b-dropdown-item>
            </div>
          </b-nav-item-dropdown>
          <b-nav-item>Random</b-nav-item>
        </b-navbar-nav>
        <b-navbar-nav class="ml-auto">
          <b-nav-form>
            <b-form-input
              size="sm"
              class="mr-sm-2"
              placeholder="Buscar"
            ></b-form-input>
            <b-button size="sm" class="my-2 my-sm-0" type="submit"
              >Buscar</b-button
            >
          </b-nav-form>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class NavBar extends Vue {
  @Prop() private msg!: string;

  categories = [];

  mounted() {
    this.getData();
  }
  async getData() {
    const response = await fetch("https://jsonfy.com/categories");
    const json = await response.json();
    this.categories = json;
    //console.log(json);
  }
}
</script>

<style scoped></style>
