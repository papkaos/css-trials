<template>
  <div class="grid-page">
    <div class="grid-header grid-box">
      <app-menu></app-menu>
    </div>
    <div class="grid-main">
      <aside class="grid-sidebar grid-box">Sidebar</aside>
      <div class="grid-content grid-box">
        <div class="grid-content-list">
          <div
            class="grid-content-item"
            v-for="post in posts"
          >
            <h3>{{ post.title }}</h3>
            <p>{{ post.body }}</p>
          </div>
        </div>
      </div>
    </div>
    <div class="grid-footer grid-box">
      <app-menu></app-menu>
    </div>
  </div>
</template>

<script>
  import Menu from "./Menu";

  export default {
    components: {
      'app-menu': Menu
    },
    data() {
      return {
        posts: []
      }
    },
    created() {
      this.$http.get('https://jsonplaceholder.typicode.com/posts').then(response => {
        this.posts = response.data;
        console.log(this.posts);
      });
    }
  }
</script>

<style lang="scss" scoped>
  .grid-box {
    padding: 20px;
    box-sizing: border-box;
  }

  .grid-page {
    display: grid;
    grid-template-rows: 58px auto 58px;
    min-height: inherit;
  }

  .grid-header {
    background-color: #67a4ff;
    z-index: 99;
  }

  .grid-main {
    display: grid;
    grid-template-columns: 260px auto;
  }

  .grid-sidebar {
    box-shadow: -3px 0 14px 0 #333;
  }

  .grid-content-list {
    display: grid;
    grid-template-columns: auto auto auto;
    grid-gap: 10px;
  }

  .grid-content-item {
    padding: 20px;
    box-shadow: 0px 0px 3px 0px #333;
    box-sizing: border-box;
  }

  .grid-footer {
    background-color: #67a4ff;
  }
</style>