<template>

  <div class = "container">
    <PageHeader title="Weather display" />

  </div>
  <SideBar  />
</template>

<script>
import PageHeader from './components/PageHeader.vue'
import SideBar from './components/PageSideBar.vue'

export default {
  name: 'App',
  components: {
    PageHeader,
    SideBar,

  },
  data() {
    return{
      PageSideBarOptions: []
    }
  },

  created() {
    
  },

}

</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');

*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Poppins', sans-serif;
}

.container {
  max-width: 1200px;
  margin: 30px auto;
  max-height: 120px;
  
  
  border: 1px solid #142559;
  padding: 30px;
  border-radius: 5px;
}

</style>
