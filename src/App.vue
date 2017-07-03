<template>
  <v-app id="app">
    <v-navigation-drawer persistent v-model="drawer" light enable-resize-watcher>
      <v-list dense>
        <v-list-item>
          <v-list-tile @click.native.stop="left = !left">
            <v-list-tile-action>
              <v-icon>exit_to_app</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title>Open Temporary Drawer</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-navigation-drawer persistent v-model="drawerRight" light right light enable-resize-watcher>
      <v-list dense>
        <v-list-item>
          <v-list-tile @click.native.stop="right = !right">
            <v-list-tile-action>
              <v-icon>exit_to_app</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title>Open Temporary Drawer</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar class="indigo" light>
      <v-toolbar-side-icon light @click.native.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-title>Toolbar</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-side-icon light @click.native.stop="drawerRight = !drawerRight"></v-toolbar-side-icon>
    </v-toolbar>
    <main>
      <v-navigation-drawer
        temporary
        v-model="left"
      ></v-navigation-drawer>
      <v-container fluid>
        <!--v-router-->
        <router-view></router-view>
      </v-container>
      <v-navigation-drawer
        right
        temporary
        v-model="right"
      ></v-navigation-drawer>
    </main>
    <v-footer class="indigo">
      <span>© 2017</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
@font-face {
  font-family: 'Material Icons';
  font-style: normal;
  font-weight: 400;
  src: url(assets/fonts/iconfont/MaterialIcons-Regular.eot); /* For IE6-8 */
  src: local('Material Icons'),
       local('MaterialIcons-Regular'),
       url(assets/fonts/iconfont/MaterialIcons-Regular.woff2) format('woff2'),
       url(assets/fonts/iconfont/MaterialIcons-Regular.woff) format('woff'),
       url(assets/fonts/iconfont/MaterialIcons-Regular.ttf) format('truetype');
}

.material-icons {
    font-family: 'Material Icons';
    font-weight: normal;
    font-style: normal;
    font-size: 24px;
    line-height: 1;
    letter-spacing: normal;
    text-transform: none;
    display: inline-block;
    white-space: nowrap;
    word-wrap: normal;
    direction: ltr;
    -webkit-font-feature-settings: 'liga';
    -webkit-font-smoothing: antialiased;
}
</style>
