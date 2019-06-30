<template>
  <div class="menu">
    <ul class="menu--list">
      <li class="menu--item">
        <a class="menu--item-link" href="#">Home</a>
      </li>
      <li class="menu--item">
        <a class="menu--item-link" href="#">Catalog</a>
      </li>
      <li class="menu--item">
        <a class="menu--item-link" href="#">Contacts</a>
      </li>
      <li class="menu--item">
        <a class="menu--item-link" href="#">FAQ</a>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
  }
</script>

<style lang="scss" scoped>
  .menu--list {
    list-style: none;
    display: flex;
    justify-content: flex-start;
    margin: 0;
    padding: 0;
  }

  .menu--item {
    height: 100%;
  }

  .menu--item-link {
    display: block;
    padding-left: 15px;
    padding-right: 15px;
    color: #ffffff;
    text-decoration: none;
  }
</style>