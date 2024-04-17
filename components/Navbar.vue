<template>
  <div>
    <nav>
      <div class="logo">
        <NuxtLink to="/home">
          <img src="/assets/images/allma_logo.svg" alt="logo" />
        </NuxtLink>
      </div>
      <button
        @click="openBurgerMenu"
        :class="isMenuOpen ? 'toggle-button-off' : 'toggle-button'"
      >
        <span class="bar"></span>
        <span class="bar"></span>
      </button>
      <div class="dropdown-menu" v-show="isMenuOpen">
        <div class="dropdown-menu__header">
          <div class="logo">
            <img src="/assets/images/allma_logo.svg" alt="logo" />
          </div>
          <div @click="closeBurgerMenu" class="close-button">
            <Icon name="material-symbols:close-rounded" color="#636363" />
          </div>
        </div>
        <ul>
          <li
            v-for="item in menuItems"
            :key="item.path"
            @click="closeBurgerMenu"
          >
            <NuxtLink :to="item.path">{{ item.name }}</NuxtLink>
          </li>
        </ul>
      </div>
      <div class="navbar-links">
        <ul>
          <li
            v-for="item in menuItems"
            :key="item.path"
            :class="{ 'active-link': isSelectedPath(item.path) }"
          >
            <NuxtLink :to="item.path">{{ item.name }}</NuxtLink>
          </li>
        </ul>
      </div>
    </nav>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { useRoute } from "vue-router";

const route = useRoute();
const isMenuOpen = ref(false);

const menuItems = [
  { name: "Home", path: "/home" },
  { name: "Team", path: "/team" },
  { name: "Collaborations", path: "/collaborations" },
  { name: "Contribute", path: "/contribute" },
  { name: "Blogs", path: "/blogs" },
  { name: "Resources", path: "/resources" },
];

function isSelectedPath(path) {
  return route.path === path || route.path === `/${path}`;
}

function openBurgerMenu() {
  isMenuOpen.value = true;
}

function closeBurgerMenu() {
  isMenuOpen.value = false;
}
</script>

<style lang="scss" scoped>
nav {
  height: 64px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo {
  padding-left: 30px;
  img {
    width: 115px;
    height: 50px;
  }
}

.active-link a {
  font-weight: bold;
}

.navbar-links {
  display: none;
}

.toggle-button-off {
  display: none;
}

.toggle-button {
  cursor: pointer;
  margin: 0;
  padding: 0;
  border: none;
  display: flex;
  flex-direction: column;
  gap: 9px;
  cursor: pointer;
  margin-right: 60px;
}

.toggle-button .bar {
  width: 20px;
  height: 2px;
  background-color: #999999;
}

.dropdown-menu {
  width: 100%;
  z-index: 100;
  background-color: #f5f3ef;
  height: 100%;
  overflow-y: hidden;
  top: 0;
  position: absolute;
  ul {
    list-style: none;
    margin: 0;
    padding: 0 0 0 50px;
    font-size: 32px;
    font-weight: 600;
    li {
      margin-bottom: 5px;
      a {
        text-decoration: none;
        color: #000;
      }
    }
  }
}

.dropdown-menu__header {
  height: 64px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin: 0 60px 20px 0;
  .close-button {
    svg {
      width: 30px;
      height: 30px;
    }
  }
}

@media (min-width: 950px) {
  .toggle-button {
    display: none;
  }

  .navbar-links {
    display: flex;
    ul {
      display: flex;
      flex-direction: row;
      justify-content: flex-end;
      gap: 1.25rem;
      list-style: none;
      padding: 1.063rem 3.125rem 1.063rem 0;
      margin: 0;
      li {
        a {
          font-size: 15px;
          text-decoration: none;
          color: #666666;
        }
      }
    }
  }

  .dropdown-menu {
    display: none;
  }
}
</style>
