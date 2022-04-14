<template>
  <div class="header">
    <Search id="search" />
    <UserEntity id="user" />
    <Address />
  </div>
</template>

<style scoped>
.header {
  margin-top: 30px;
  margin-left: 50px;
  position: relative;
}

#search {
  width: 700px;
  display: inline-block;
  vertical-align: middle;
}

#user {
  position: absolute;
  top: 50%;
  transform: translate(0, -50%);
  right: 30px;
  vertical-align: middle;
}
</style>
