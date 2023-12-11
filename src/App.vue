<template>
  <div id="app">
   <CursorFollower/>
  </div>
</template>

<script>
import CursorFollower from "@/components/CursorFollower.vue"
export default {
  data() {
    return {
      
    };
  },
  components:{
    CursorFollower
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
