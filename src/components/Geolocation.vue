<template>
  <div>
    <div id="title">
        Geolocation API
    </div>
    <button v-on:click="GetPosition">Get Position</button>
    <p v-if="isCorrespond">対応しています</p>
    <p v-else>対応していません</p>
  </div>
</template>

<script>
   export default {
       data(){
           return {
               isCorrespond: false
           }
       },
       created(){
           if(navigator.geolocation){
               this.isCorrespond = true;
           }
       },
       methods: {
           GetPosition: function () {
               navigator.geolocation.watchPosition(
                   function(position) {
                       console.log(position);
                       alert("緯度:" + position.coords.latitude + ",経度" + position.coords.longitude + ",方角" + position.coords.heading);
                   },
                   function(error) {
                       switch(error.code) {
                           case 1:
                            alert("PERMISSION_DENIED");
                            break;
                           case 2:
                            alert("POSITION_UNAVAILABLE");
                            break;
                           case 3:
                            alert("TIMEOUT");
                            break;
                           default:
                            alert(error.code);
                            break;
                       }
                   },
                   {
                       enableHighAccuracy: true
                   }
               );
           }
       }
   }
</script>

<style>
#title {
  text-align: center;
  font-size: 200%;
}
</style>