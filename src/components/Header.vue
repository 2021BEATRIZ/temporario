<template>
  <header>
    <nav class="container">
      <router-link to="/">
        <a href="/"><img alt="Papel-Moeda" id="logo" src="@/assets/logo-Papel-Moeda.png" /></a>
        <span class="papel-moeda">Papel-Moeda</span>
      </router-link>

      <img v-on:click="openMenu" alt="Abrir menu" id="menu-button" src="@/assets/menu-mobile.png" />

      <div v-on:click="closeMenu" id="menu-overlay" v-if="menuActive"></div>

      <div id="menu-items" :class="{ active: menuActive }">
        <a href="/"><img alt="Papel-Moeda" id="menu-logo" src="@/assets/logo-Papel-Moeda.png" /></a>

        <ul>
          <li><a href="/">cursos</a></li>
          <li><a href="/painel">painel administrativo</a></li>
        </ul>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      menuActive: true,
    };
  },
  methods: {
    openMenu: function () {
      this.menuActive = true;
    },
    closeMenu: function () {
      this.menuActive = false;
    },
  },
};
</script>

<style scoped>
header {
  font-family: Ubuntu;
  font-style: normal;
  font-weight: bold;
  background-color: var(--color-background-nav);
  width: 100%;
  height: 60px;
  display: flex;
  justify-content: center;
  align-items: center;
}

nav {
  display: flex;
  justify-content: space-between;
  height: 60px;
  align-items: center;
}

#logo {
  width: 40px;
}

#menu-button {
  width: 30px;
}

#menu-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 40%;
  height: 100vh;
  background-color: black;
  opacity: 0.8;
}

#menu-logo {
  width: 40px;
  margin-top: 30px;
  margin-bottom: 10px;
}

#menu-items {
  position: fixed;
  top: 0;
  right: 0;
  background-color: var(--color-background-nav);
  width: 60%;
  height: 100vh;
  display: none;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
}

#menu-items.active {
  display: flex;
}

ul {
  font-size: 22px;
  list-style: none;
  text-align: center;
}

ul li {
  margin: 20px 0px;
}

ul li a {
  color: var(--color-text-light);
}

.papel-moeda {
  font-family: Ubuntu;
  font-style: normal;
  font-weight: bold;
  font-size: 36px;
  line-height: 23px;
  padding: 5px;
  color: #FFFFFF;
}

@media (min-width: 700px) {
  #menu-button,
  #menu-logo,
  #menu-overlay {
    display: none;
  }

  #menu-items {
    display: flex;
    position: static;
    height: 60px;
    width: auto;
  }

  ul {
    display: flex;
    height: 60px;
    align-items: center;
  }

  ul li {
    margin: 0;
    margin-left: 20px;
  }
}
</style>