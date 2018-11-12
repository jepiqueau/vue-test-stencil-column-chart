<template>
  <ion-app>
    <ion-header>
    <ion-toolbar color="primary">
        <ion-buttons slot="start">
            <!--
                *** does not work
            <ion-back-button defaultHref="/"></ion-back-button>
            -->
          <ion-button @click="goBackHome()" size="small">Back</ion-button>
        </ion-buttons>
        <ion-title>Columnchart</ion-title>
    </ion-toolbar>
    </ion-header>

    <ion-content>
        <template v-if="this.type === 'allpositive'">
            <jeep-columnchart ctitle="Basic Column Chart" subtitle="test sub-title" 
                xtitle="test for x axis" ytitle="test for y axis" 
                datapoints='{"data":[
                {"label":"Apple","y":10,"color":"#e34c46"},
                {"label":"Orange","y":17,"color":"#d1b038"},
                {"label":"Banana","y":12,"color":"#48a37c"},
                {"label":"Mango","y":30,"color":"#111782"},
                {"label":"Grape","y":28,"color":"#db123a"}]}'
                animation cborder>
            </jeep-columnchart>
        </template>
        <template v-if="this.type === 'allnegative'">
            <jeep-columnchart ctitle="Basic Column Chart" subtitle="test sub-title" 
                xtitle="test for x axis" ytitle="test for y axis" 
                datapoints='{"data":[
                {"label":"Apple","y":-20,"color":"#e34c46"},
                {"label":"Orange","y":-17,"color":"#d1b038"},
                {"label":"Banana","y":-15,"color":"#48a37c"},
                {"label":"Mango","y":-30,"color":"#111782"},
                {"label":"Grape","y":-25,"color":"#db123a"}]}'
                animation>
            </jeep-columnchart>
        </template>
        <template v-if="this.type === 'cstyle'">
            <jeep-columnchart ctitle="Basic Column Chart" subtitle="test sub-title" 
                xtitle="test for x axis" ytitle="test for y axis" 
                datapoints='{"data":[
                {"label":"Apple","y":10,"color":"#e34c46"},
                {"label":"Orange","y":-17,"color":"#d1b038"},
                {"label":"Banana","y":12,"color":"#48a37c"},
                {"label":"Mango","y":-30,"color":"#111782"},
                {"label":"Grape","y":28,"color":"#db123a"}]}'
                animation cborder
            cstyle="--height:450px;--width:80%;--top:30px;--left:10%;">
            </jeep-columnchart>
        </template>
        <template v-if="this.type === 'multipleplots'">
            <div>
                <jeep-columnchart ctitle="Basic Column Chart" subtitle="test sub-title" 
                    xtitle="test for x axis" ytitle="test for y axis" 
                    datapoints='{"data":[
                    {"label":"Apple","y":10,"color":"#e34c46"},
                    {"label":"Orange","y":17,"color":"#d1b038"},
                    {"label":"Banana","y":12,"color":"#48a37c"},
                    {"label":"Mango","y":30,"color":"#111782"},
                    {"label":"Grape","y":28,"color":"#db123a"}]}'
                    cborder
                    cstyle="--height:250px;--width:70%;--top:20px;--left:10%;--backgroundcolor: rgb(248, 243, 222);">
                </jeep-columnchart>
                <jeep-columnchart ctitle="Basic Column Chart" subtitle="test sub-title" 
                    xtitle="test for x axis" ytitle="test for y axis" 
                    datapoints='{"data":[
                    {"label":"Apple","y":10,"color":"#e34c46"},
                    {"label":"Orange","y":17,"color":"#d1b038"},
                    {"label":"Banana","y":12,"color":"#48a37c"},
                    {"label":"Mango","y":30,"color":"#111782"},
                    {"label":"Grape","y":28,"color":"#db123a"}]}'
                    animation cborder
                    cstyle="--height:350px;--width:95%;--top:20px;--left:2.5%;">
                </jeep-columnchart>
            </div>
        </template>
    </ion-content>
  </ion-app>
</template>

<script>
export default {
  name: "columnchart",
  data() {
      return {
          type: this.$route.params.type
      }
  },
  methods: {
    goBackHome: function() {
      this.$router.push("/");
    }
  }  
};
</script>
