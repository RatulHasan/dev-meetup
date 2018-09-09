<template>
    <v-app>
        <v-navigation-drawer v-model="sideNav" absolute temporary>
            <v-list class="pa-1">
                <v-list-tile avatar>
                    <v-list-tile-avatar>
                        <img src="https://randomuser.me/api/portraits/men/85.jpg">
                    </v-list-tile-avatar>

                    <v-list-tile-content>
                        <v-list-tile-title>John Leider</v-list-tile-title>
                    </v-list-tile-content>
                </v-list-tile>
            </v-list>

            <v-list class="pt-0" dense>

                <v-divider></v-divider>

                <v-list-tile
                        v-for="item in items"
                        :key="item.title"
                        @click=""
                >
                    <v-list-tile-action>
                        <v-icon>{{ item.icon }}</v-icon>
                    </v-list-tile-action>

                    <v-list-tile-content>
                        <v-list-tile-title>{{ item.title }}</v-list-tile-title>
                    </v-list-tile-content>
                </v-list-tile>
            </v-list>
        </v-navigation-drawer>
        <v-toolbar>
            <v-toolbar-side-icon @click.native.stop="sideNav = !sideNav"></v-toolbar-side-icon>
            <v-toolbar-title>Title</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-toolbar-items class="hidden-sm-and-down">
                <v-btn flat>
                    <v-icon left>home</v-icon>
                    Home
                </v-btn>
                <v-btn flat>
                    <v-icon left>supervisor_account</v-icon>
                    View Meetups
                </v-btn>
                <v-btn flat>
                    <v-icon left>create</v-icon>
                    Blog
                </v-btn>
            </v-toolbar-items>
        </v-toolbar>

        <main>
            <router-view></router-view>
        </main>
    </v-app>
</template>

<script>
  /* eslint-disable */
  import VDivider from 'vuetify/src/components/VDivider/VDivider'

  export default {
    components: {VDivider},
    data () {
      return {
        sideNav: false,
        items: [
          { title: 'Home', icon: 'dashboard' },
          { title: 'About', icon: 'question_answer' }
        ]
      }
    },
    name: 'App'
  }
</script>