<template>
  <div class="flex-page">
    <div class="flex-header flex-box">
      <app-menu></app-menu>
    </div>
    <div class="flex-main">
      <aside class="flex-sidebar flex-box">Sidebar</aside>
      <div class="flex-content flex-box">
        <div class="flex-content-list">
          <div
            class="flex-content-item"
            v-for="post in posts"
          >
            <h3>{{ post.title }}</h3>
            <p>{{ post.body }}</p>
          </div>
        </div>
      </div>
    </div>
    <div class="flex-footer flex-box">
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

<style scoped>
  .flex-box {
    padding: 20px;
    box-sizing: border-box;
  }

  .flex-page {
    display: flex;
    flex-direction: column;
    min-height: inherit;
  }

  .flex-header {
    flex: 0 0;
    background-color: #67a4ff;
    z-index: 99;
  }

  .flex-main {
    display: flex;
    flex-direction: row;
    flex-grow: 1;
  }

  .flex-sidebar {
    width: 260px;
    flex-grow: 0;
    flex-shrink: 0;
    box-shadow: -3px 0 14px 0 #333;
  }

  .flex-content {
    flex-grow: 1;
  }

  .flex-content-list {
    display: flex;
    flex-wrap: wrap;
    margin: -5px;
  }

  .flex-content-item {
    width: 30%;
    flex-grow: 1;
    margin: 5px;
    padding: 20px;
    box-shadow: 0px 0px 3px 0px #333;
    box-sizing: border-box;
  }

  .flex-footer {
    flex: 0 0;
    background-color: #67a4ff;
  }
</style>