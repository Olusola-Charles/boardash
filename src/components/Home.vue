<template>
  <v-app>
    <v-navigation-drawer app clipped permanent mt="20">
      <v-toolbar></v-toolbar>
      <v-toolbar flat>
        <v-list>
          <v-list-tile>
            <v-list-tile-title class="title">Filter</v-list-tile-title>
          </v-list-tile>
        </v-list>
      </v-toolbar>
    </v-navigation-drawer>

    <v-toolbar app clipped-left class="elevation-1">
      <span>Toolbar1</span>
    </v-toolbar>

    <v-toolbar app class="mt-5 elevation-1" style="top: 16px">
      <span>Toolbar2</span>
    </v-toolbar>

    <v-content class="mt-5">
      <HomePage/>
    </v-content>
  </v-app>
</template>
