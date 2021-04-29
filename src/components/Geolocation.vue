<template>
  <dev>
    <dev id = "title">
        Geolocation API
    </dev>
    <button v-on:click="GetPosition">Get Position</button>
  </dev>
</template>

<script>
   export default {
       methods: {
           GetPosition: function () {
               navigator.geolocation.getCurrentPosition(
                   function(position) {
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