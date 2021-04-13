<template>
  <div id="nav">
    <router-link to="/">Infos personnels</router-link> |
    <router-link to="/ProInfo">Info professionnelles</router-link> |
    <router-link to="/Profile">Employee Profil</router-link>
  </div>
  <router-view/>
</template>

<style>
#app {
  text-align: center;
  
}

#nav {
  padding: 50px;
  background-color: black;
}

#nav a {
  font-size: 17px;
  color: white;
  list-style-type:none;
}

#nav a.router-link-exact-active {
  color: grey;
}

</style>
