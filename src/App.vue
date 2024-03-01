<script setup>
import { ref } from 'vue';
import { useRouter } from 'vue-router';
import MenuItem from './components/MenuItem.vue';

const router = useRouter();

const menuItems_old = ref([
  { id: 1, name: 'Home', route: 'home', params: "1" },
  { id: 2, name: 'About', route: 'about', params: "cippa" },
  { id: 3, name: 'Contact', route: 'contact', params: "3" },
]);

const menuItems = ref([
  { id: 1, name: 'Home', route: 'home', params: "1", icon: 'M10 20V14H14V20H19V12H22L12 3L2 12H5V20H10Z' },
  { id: 2, name: 'About', route: 'about', params: "cazzone", icon: 'M12 2A9 9 0 0 0 3 11H0L4 15L8 11H5A7 7 0 0 1 12 4A7 7 0 0 1 19 11H16L20 15L24 11H21A9 9 0 0 0 12 2Z' },
  { id: 3, name: 'Contact', route: 'contact', params: "3", icon: 'M12 2A10 10 0 0 0 2 12A10 10 0 0 0 12 22A10 10 0 0 0 22 12A10 10 0 0 0 12 2M12 4A8 8 0 0 1 20 12A8 8 0 0 1 12 20A8 8 0 0 1 4 12A8 8 0 0 1 12 4M12 6A1.5 1.5 0 0 0 10.5 7.5A1.5 1.5 0 0 0 12 9A1.5 1.5 0 0 0 13.5 7.5A1.5 1.5 0 0 0 12 6M7 9H9V11H7V9M15 9H17V11H15V9Z' },
]);

const showMenu = ref(false);

const navigate = (item) => {
  router.push({ name: item.route, params: { id: item.params }});
  showMenu.value = false; // close the menu after navigation
};

const toggleMenu = () => {
  showMenu.value = !showMenu.value;
};

</script>

<template>
  <div class="container">
    <button class="hamburger" @click="toggleMenu">
      <span>&#9776;</span> <!-- hamburger icon -->
    </button>
    <div class="menu" v-show="showMenu">
      <MenuItem 
        v-for="item in menuItems" 
        :key="item.id" 
        :item="item" 
        @click="navigate(item)" 
      />
    </div>
    <div class="content">
      <router-view />
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  position: relative;
}

.hamburger {
  position: absolute;
  top: 10px;
  left: 10px;
  background: none;
  border: none;
  font-size: 30px;
  cursor: pointer;
  z-index: 2;
}

.menu {
  flex: 0;
  display: flex;
  flex-direction: column;
  background-color: #f0f0f0; /* light gray */
  margin-right: 10px;
  transition: transform 0.5s ease-in-out;
  transform: translateX(0);
  /* position: absolute; */
  top: 0;
  left: 0;
  height: 100vh;
  padding-top: 50px;
}

.menu[v-show="true"] {
  transform: translateX(0);
}

.content {
  flex: 2;
  background-color: #ffffff; /* white */
  z-index: 1;
}
</style>