<template>
  <div class="app-main-layout">
    <Navbar @toggleSidebar="toggleSidebar" />
    <SideBar :isOpen=isOpen />

    <main class="app-content" :class="{full:!isOpen}">
      <div class="app-page">
        <router-view />
      </div>
    </main>

    <div class="fixed-action-btn">
      <router-link to="/record" class="btn-floating btn-large blue">
        <i class="large material-icons">add</i>
      </router-link>
    </div>
  </div>
</template>
<script>
import Navbar from "@/components/app/Navbar";
import SideBar from "@/components/app/SideBar";

export default {
  name: "main-layout",
  data: () => ({
    isOpen: true
  }),
  methods: {
    toggleSidebar() {
      this.isOpen = !this.isOpen;
    }
  },
  components: {
    Navbar,
    SideBar
  }
};
</script>
