<template>
  <div class="sidebar">
    <nav class="sidebar-nav">
      <sidebar-item :routes='menus'></sidebar-item>

    </nav>
  </div>
</template>
<script>
import SidebarItem from './SidebarItem';
import { mapGetters } from 'vuex';
import menus from '../menu-config';

export default {
  name: 'sidebar',
  data() {
    return {
      menus: menus
    }
  },
  components: { SidebarItem },
      computed: {
        ...mapGetters([
          'siderbar_routers'
        ])
      },
  methods: {
    handleClick (e) {
      e.preventDefault()
      e.target.parentElement.classList.toggle('open')
    }
  }
}
</script>

<style lang="css">
  .nav-link {
    cursor:pointer;
  }
</style>
