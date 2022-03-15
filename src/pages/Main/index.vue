<template>
    <div> 
      <Tab />
      <router-view></router-view>
    </div>
   
</template>

<script>
// import HelloWorld from '@/components/HelloWorld.vue'
import Tab from '@/components/Tab.vue'


export default {
  
    components:{
        Tab

    }
    
}
</script>

<style>

</style>