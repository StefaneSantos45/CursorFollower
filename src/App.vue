<template>
  <div id="app">
   <ExpandingPanels/>
  </div>
</template>

<script>
import ExpandingPanels from "@/components/ExpandingPanels.vue"
export default {
  data() {
    return {
      
    };
  },
  components:{
    ExpandingPanels
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
