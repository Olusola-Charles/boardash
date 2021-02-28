<template>
  <div>
    <v-container>
     <v-row>
      <v-col cols="12" sm="6">
       <span class="caption">Messages</span>
       <v-spacer left></v-spacer>
      </v-col>    
      <v-col cols="12">
        <v-btn color="white">
          <v-icon>fas fa-chevron-left</v-icon>1-50 pages
          <v-icon>fas fa-chevron-right</v-icon>   
        </v-btn>       
      </v-col>
      <v-col>
       <v-btn color="blue">
          <span class="caption">ALL</span>
       </v-btn>
       </v-col>
      <v-col>
       <v-btn color="white">
          <span class="caption">Unread</span>
       </v-btn>
       </v-col>
       <v-col>
       <v-btn color="white">
          <span class="caption">Important</span>
       </v-btn>
       </v-col>
     </v-row>
    </v-container>
    <v-divider> </v-divider>
    <v-container flat class="ml-16">
     <v-tabs>
      <v-tab>
       <v-btn fab color="purple lighten-4">
         <v-icon>far fa-comment-alt </v-icon>
          <span class="caption">Overall Messages</span><br><strong>2389</strong>This year
        </v-btn>
       </v-tab>
       <v-tab>
       <v-btn fab color="purple lighten-4">
         <v-icon>fas fa-reply </v-icon>
          <span class="caption">Sent Messages</span><br><strong>1494</strong>This year
       </v-btn> 
       </v-tab>
       <v-tab>
       <v-btn fab color="purple lighten-4">
         <v-icon>fas fa-reply</v-icon>
          <span class="caption">Received Messages</span><br><strong>895</strong>This year
       </v-btn>
       </v-tab>
     </v-tabs>
     <v-spacer></v-spacer>
     <v-btn fab color="purple lighten-4">
      <v-icon>fas fa-bell </v-icon>Set alert
     </v-btn>
     <v-avatar size="40" class="mx-2">
      <v-img src="http://cdn.vuetifyjs.com/images/lists/3.jpg"></v-img>
     </v-avatar>Essie Howell
    </v-container>
  </div>
</template>

<script>
  
  export default{
    name: "Home",
    data: () => ({
      tab: null,
      text: "center",
      fill: true,
      padding: 8,
      radius: 10,
      value: [0, 2, 5, 9, 5, 10, 3, 5, 0, 0 , 1, 8, 2, 9, 0],
      width: 2,
      lineCap: "round",
      autoLineWidth: false,
      fills: false
    })
  }
</script>
