<template>
  <v-navigation-drawer class="py-6" v-model="drawer" app :style="{ background: '#3D366A' }" mini-variant mini-variant-width="80">
    <v-avatar class="d-block text-center mx-auto mt-4" size="40">
      <v-icon color="#A4BEF3" large>fab fa-atlassian</v-icon>
    </v-avatar>
    <v-divider class="mx-3 my-5"></v-divider>
    <v-list flat class="mt-5 text-center">
      <v-list-item-group>
        <v-list-item v-for="(item, i) in items" :key="i" active-class="border text-center" :ripple="false">
          <v-list-item-icon>
            <v-icon class="white--text" v-text="item.icon"></v-icon>
          </v-list-item-icon>
        </v-list-item>
      </v-list-item-group>
    </v-list>
    <div style="position: absolute; bottom: 50px; margin-left: auto; margin-right: auto; left: 0; right: 0; text-align: center;">
      <v-btn icon :ripple="false">
        <v-badge bordered overlap color="red" dot>
          <v-icon class="white--text">far fa-bell</v-icon>
        </v-badge>
      </v-btn>
      <br>
      <v-avatar size="30">
        <v-img src="https://cdn.vuetifyjs.com/images/lists/1.jpg"/>
      </v-avatar>
    </div>
  </v-navigation-drawer>
</template>

<script>
  export default {
    name: 'SideBar',
    data: () => ({
      selectItem: 0,
      drawer: null,
      items: [
        {icon: 'fas fa-plus'},
        {icon: 'fas fa-th-large'},
        {icon: 'fas fa-align-center'},
        {icon: 'fab fa-gitter'},
        {icon: 'fas fa-chart-line'}
      ]
    }),
  }
</script>

<style lang="scss" scoped>
  .border {
    margin-left: 12px;
    margin-right: 12px;
    background: #A4BEF3;
    border-radius: 50%;
    text-decoration: none;
  }

  .v-list-item-group .v-list-item--active {
    color: white !important;
  }
</style>