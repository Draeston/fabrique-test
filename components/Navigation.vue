<template>
  <aside>
    <ul>
      <li class="margin-bottom-30">
        <NuxtLink exact to="/">
          <div>
            <img src="/nav-icons/home.png" alt="">
          </div>
        </NuxtLink>
      </li>
      <li>
        <NuxtLink to="/surveys">
          <div>
            <img src="/nav-icons/surveys.png" alt="">
            <p>Опросы</p>
          </div>
        </NuxtLink>
      </li>
      <li>
        <NuxtLink to="/users">
          <div>
            <img src="/nav-icons/users.png" alt="">
            <p>Пользователи</p>
          </div>
        </NuxtLink>
      </li>
      <li>
        <NuxtLink to="/blacklist">
          <div>
            <img src="/nav-icons/blacklist.png" alt="">
            <p>Черные списки</p>
          </div>
        </NuxtLink>
      </li>
      <li>
        <NuxtLink to="/callcenter">
          <div>
            <img src="/nav-icons/callcenter.png" alt="">
            <p>Колл-центр</p>
          </div>
        </NuxtLink>
      </li>
    </ul>
  </aside>
</template>

<style scoped>
aside {
  position: fixed;
  left: 0;
  top: 0;

  width: 120px;
  padding: 5px;
  height: 100%;
  border-right: 1px solid lightgray;
}

a {
  color: black;
  text-decoration: none;
}

a.nuxt-link-active > div {
  font-weight: bold;
  background: lightgray;
}

img {
  width: 30%;
}

ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  text-align: center;
}

li {
  display: block;
  border-radius: 4px;
  margin-top: 10px;
}

li:hover {
  background: lightgray;
}

p {
  margin-top: 5px;
}

div {
  padding-bottom: 5px;
  padding-top: 5px;
}

.margin-bottom-30 {
  margin-bottom: 30px;
}
</style>
