<template>
  <v-navigation-drawer class="py-6" app :style="{ background: '#3D366A' }" right width="290">
    <v-toolbar color="rgba(0,0,0,0)" flat>
      <v-toolbar-title class="white--text">Epics</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn rounded small>
        See All
      </v-btn>
    </v-toolbar>
    <v-list subheader two-line class="mt-n4">
      <v-list-item v-for="file in files" :key="file.tile">
        <v-list-item-avatar>
          <v-icon :class="file.color" dark v-text="file.icon" small></v-icon>
        </v-list-item-avatar>
        <v-list-item-content>
          <v-list-item-title class="white--text" v-text="file.title"></v-list-item-title>
          <v-list-item-subtitle class="white--text" v-text="file.subtitle"></v-list-item-subtitle>
        </v-list-item-content>
        <v-list-item-action>
          <v-btn icon>
            <v-icon color="grey ligthen-1" small>fas fa-ellipsis-h</v-icon>
          </v-btn>
        </v-list-item-action>
      </v-list-item>
    </v-list>
    <v-toolbar color="rgba(0,0,0,0)" flat class="mt-n6">
      <v-toolbar-title class="white--text">Project statistics</v-toolbar-title>
    </v-toolbar>
    <v-card class="mx-2 rounded-1-xl pb-1" flat color="#393162">
      <v-row>
        <v-col cols="12" sm="5">
          <v-list-item two-line class="mt-n4">
            <v-list-item-content>
              <v-list-item-title class="white--text">
                Project
              </v-list-item-title>
              <v-list-item-subtitle class="white--text">
                progress
              </v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-col>
        <v-col cols="12" sm="4">
          <v-progress-circular :size="56" :width="3" :value="75" color="#A4BEF3">
            75%
          </v-progress-circular>
        </v-col>
      </v-row>
    </v-card>

    <v-card class="my-3 mx-2 rounded-1-xl pb-1" flat color="#393162">
      <v-row>
        <v-col cols="12" sm="5">
          <v-list-item two-line class="mt-n4">
            <v-list-item-content>
              <v-list-item-title class="white--text">
                Business
              </v-list-item-title>
              <v-list-item-subtitle class="white--text">
                progress
              </v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-col>
        <v-col cols="12" sm="4">
          <v-progress-circular :size="56" :width="3" :value="35" color="#A4BEF3">
            35%
          </v-progress-circular>
        </v-col>
      </v-row>
    </v-card>
    
    <v-card class="mx-2 rounded-1-xl pb-1" flat color="#393162">
      <v-row>
        <v-col cols="12" sm="5">
          <v-list-item two-line class="mt-n4">
            <v-list-item-content>
              <v-list-item-title class="white--text">
                Design
              </v-list-item-title>
              <v-list-item-subtitle class="white--text">
                progress
              </v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-col>
        <v-col cols="12" sm="4">
          <v-progress-circular :size="56" :width="3" :value="52" color="#A4BEF3">
            52%
          </v-progress-circular>
        </v-col>
      </v-row>
    </v-card>
    <div class="mt-2 mx-2">
      <v-btn rounded small block>
        Project Details
      </v-btn>
    </div>
  </v-navigation-drawer>
</template>

<script>
  export default {
    name: 'SideBarRight',
    data: () => ({
      files: [
        {
          color: 'green',
          icon: 'fas fa-mobile',
          subtitle: 'Design',
          title: 'Mobile Onboarding'
        },
        {
          color: 'red',
          icon: 'fas fa-user-shield',
          subtitle: 'development',
          title: 'Admin Panel'
        },
        {
          color: 'orange',
          icon: 'fas fa-drafting-compass',
          subtitle: 'Design & Development',
          title: 'Mobile MVP'
        },
        {
          color: 'purple',
          icon: 'fas fa-file-code',
          subtitle: 'Research',
          title: 'QR Scann'
        }
      ]
    })
  }
</script>

<style lang="scss" scoped>

</style>