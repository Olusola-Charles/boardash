<template>
  <v-app id="inspire">
    <v-system-bar app color="white" height="50">
     <p class="font-weight-black pt-4 pr-8 pl-4">
       BOARDASH
     </p> 
      <v-text-field placeholder="Search message, people, tickets" class="pt-4">
          append-icon="mdi-forum"></v-text-field>
      <p class="pt-4 px-5">
        <v-icon>mdi-bell</v-icon>
        <v-text> set alert</v-text>
      </p>
     <v-avatar size="40" class="6">
      <v-img src="http://cdn.vuetifyjs.com/images/lists/3.jpg"></v-img>
     </v-avatar><p class="pl-2 pr-5 pt-5">Essie Howell</p>
      <v-icon>mdi-circle</v-icon>
    </v-system-bar>

    <v-navigation-drawer v-model="drawer"
      app permanent clipped >
      <v-sheet
        color="grey lighten-4"
        class="pa-7"
      >
        <v-avatar class="mb-4" color="grey darken-1"
          size="40">
         <v-img src="http://cdn.vuetifyjs.com/images/lists/3.jpg"></v-img>
        </v-avatar>
        Welcome Essie <br/>
        Super Admin
      </v-sheet>
      <v-divider></v-divider>
      <v-list>
       <v-list-item-group v-model="model" color="blue">
        <v-list-item
          v-for="[icon, text] in links"
          :key="icon"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ text }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
       </v-list-item-group>
      </v-list>
        <v-spacer></v-spacer>
            <v-icon>fas fa-power-off</v-icon>
            <v-list-item-title>Logout</v-list-item-title>
    </v-navigation-drawer>

    <v-main>

     <v-container class="pt-4 px-6" fluid>
      <v-row>
       <v-col>
        <v-card height="64" class="px-4" outlined>
         <v-text class="button my-15 pr-15">Message
         </v-text>
         <v-btn color="white" class="mx-4 px-12 mt-3" flat>
          <v-icon>fas fa-chevron-left</v-icon>1-50 pages
          <v-icon>fas fa-chevron-right</v-icon>
         </v-btn>
         <v-btn color="blue" class="mr-3 mt-3">
          <span class="caption">ALL</span>
         </v-btn>
         <v-btn color="white" class="mt-3">
          <span class="caption">Unread</span>
         </v-btn>
         <v-btn color="white" class="mt-3">
          <span class="caption">Important</span>
         </v-btn>
        </v-card>
       </v-col>
      </v-row>
     </v-container>

     <v-container class="py-1 px-6" fluid>
      <v-row>
       <v-col color="orange lighten-3">
        <v-card height="100" outlined color="orange accent-3">
         <v-avatar class="mb-4" color="grey darken-1"
          size="40">
          <v-img src="http://cdn.vuetifyjs.com/images/lists/3.jpg"></v-img>
         </v-avatar>
        </v-card>
       </v-col>
      </v-row>
     </v-container>

    <v-item-group >
     <v-container class="py-1 px-6" fluid>
      <v-row>
       <v-col>
        <v-card height="100">
         <v-btn fab color="grey lighten-3" class= "mx-16 my-4">
          <v-icon color="blue"> mdi-forum </v-icon>
         </v-btn>
         <v-btn fab color="grey lighten-3" class="mx-16 my-4">
          <v-icon color="blue">mdi-send </v-icon>
         </v-btn>
         <v-btn fab color="grey lighten-3" class="mx-16 my-4">
         <v-icon color="blue">fas fa-reply</v-icon>
         </v-btn>
        </v-card>
       </v-col>
      </v-row>
     </v-container>
    </v-item-group>
     <v-container class="py-1 px-6" fluid>
      <v-row>
       <v-col>
       <v-card>
       <template v-for="(item, index) in items">
        <v-subheader
          v-if="item.header"
          :key="item.header"
          v-text="item.header"
        ></v-subheader>

        <v-divider
          v-else-if="item.divider"
          :key="index"
          :inset="item.inset"
        ></v-divider>

        <v-list-item
          v-else
          :key="item.title"
        >
         <v-list-item-action>
              <v-checkbox
                v-model="active"
                color="primary"
                >
              ></v-checkbox>
            </v-list-item-action>
          <v-list-item-avatar>
            <v-img :src="item.avatar"></v-img>
          </v-list-item-avatar>

          <v-list-item-content>
            <v-list-item-title v-html="item.title"></v-list-item-title>
            <v-list-item-subtitle v-html="item.subtitle"></v-list-item-subtitle>
          </v-list-item-content>
         <v-list-item-action>
          <v-btn icon>
            <v-icon color="grey lighten-1">mdi-dots-vertical</v-icon>
          </v-btn>
        </v-list-item-action>
        </v-list-item>
      </template>
      </v-card>
      </v-col>
      </v-row>
     </v-container>
    </v-main>
  </v-app>
</template>

<script>
  export default {
    data: () => ({
      drawer: null,
      links: [
         ["mdi-view-dashboard", "Overview"],
         ["fas fa-bookmark", "Reservation"],
         ["fas fa-briefcase", "Meeting"],
         ["fas fa-user-friends", "Customers"],
         ["fas fa-ticket-alt", "Ticket"],
         ["mdi-forum", "Message"],
         ["fas fa-user", "Profile"]
      ],
      items: [
        { header: 'Today' },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg',
          title: 'Brunch this weekend?',
          subtitle: `<span class="text--primary">Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend. Do you want to hang out?`,
        },
        { divider: true, inset: true },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg',
          title: 'Summer BBQ <span class="grey--text text--lighten-1">4</span>',
          subtitle: `<span class="text--primary">to Alex, Scott, Jennifer</span> &mdash; Wish I could come, but I'm out of town this weekend.`,
        },
        { divider: true, inset: true },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/3.jpg',
          title: 'Oui oui',
          subtitle: '<span class="text--primary">Sandra Adams</span> &mdash; Do you have Paris recommendations? Have you ever been?',
        },
        { divider: true, inset: true },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/4.jpg',
          title: 'Birthday gift',
          subtitle: '<span class="text--primary">Trevor Hansen</span> &mdash; Have any ideas about what we should get Heidi for her birthday?',
        },
        { divider: true, inset: true },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/5.jpg',
          title: 'Recipe to try',
          subtitle: '<span class="text--primary">Britta Holt</span> &mdash; We should eat this: Grate, Squash, Corn, and tomatillo Tacos.',
        },
      ],
      model: 5,
    }),
  }
</script>
