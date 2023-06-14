<template>
     <header class="header">
    <div class="container">
        <img src="/Users/ismail/OneDrive/Desktop/Yazılım/imgders30/logo.svg" alt="Logo">

      <nav>
        <a href="#">Movies</a>
        <a href="#">TV Shows</a>
        <a href="#">
          Suggest Me
          <img src="/Users/ismail/OneDrive/Desktop/Yazılım/imgders30/arrow-right.svg" alt="Arrow">
        </a>
      </nav>
    </div>
  </header>
</template>

<script>
    export default {

    }

</script>

<style>
.header .container {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.header nav {
  display: flex;
  align-items: center;
}

.header a {
  display: flex;
  align-items: center;
  padding: 12px 16px;
  font-weight: 600;
  text-decoration: none;
  color: var(--gray-200);
}
</style>