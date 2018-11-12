<template>
  <ion-app>
    <ion-header>
      <ion-toolbar color="primary">
        <ion-title>
          Column Chart Example in Vue
        </ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content padding>
      <p>Test Columnchart Web component in Vue.js</p>
      <ion-button @click="goToAbout" size="large">Go to About</ion-button>
      <ion-button @click="goToColumnChart('allpositive')" size="large">Columns all positive</ion-button>
      <ion-button @click="goToColumnChart('allnegative')" size="large">Columns all negative</ion-button>
      <ion-button @click="goToColumnChart('cstyle')" size="large">Chart with cstyle</ion-button>
      <ion-button @click="goToColumnChart('multipleplots')" size="large">Multiple Plots</ion-button>
    </ion-content>
  </ion-app>
</template>
<script>

export default {
  name: "home",
  methods: {
    goToAbout: function() {
      this.$router.push("about");
    },
    goToColumnChart: function(type) {
      this.$router.push("columnchart/"+type);
    },
    goToTest: function(type) {
      this.$router.push("test/"+type);
    }
  }
};
</script>
