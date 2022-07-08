<template>
  <div class = "container">
    <PageHeader 
      title="Weather display"
      @toggle-menu="toggleMenu"
    />
    <div class = "widgets">
      <div 
        :key = "widget.id"
        v-for="widget in widgets"
      >
      <h1 v-if="widget.active">{{widget.name}}</h1>
      </div>
    </div>

    <div class = "settingsWindow" v-if="showWidget">
      <AddWidget 
        @widget-toggle="selectedWidgets" 
        :widgets="widgets" 
      />
    </div>
  </div>
  <ChartWidget  />

  <div class = "sidebar" v-if="showSideBar">
    <SideBar  
    @toggle-widget="toggleWidget"
    @toggle-setup="toggleSetup"
    @toggle-settings="toggleSettings"
    />
  </div>

</template>

<script>
import PageHeader from './components/PageHeader.vue'
import SideBar from './components/PageSideBar.vue'
import AddWidget from './components/AddWidget.vue'
import ChartWidget from './components/ChartWidget.vue'


export default {
  name: 'App',
  components: {
    PageHeader,
    SideBar,
    AddWidget,
    ChartWidget,
},

  data() {
    return{
      PageSideBarOptions: [],

      //showMenus
      showSideBar: false,
      showWidget: false,
      showSetup: false,
      showSettings: false,

      weatherData: [],
      widgets: [],
    }
  },
  methods:{
    toggleMenu(){
      this.showSideBar = !this.showSideBar
      this.showWidget = false
    },
    toggleWidget(){
      this.showWidget = !this.showWidget
    },
    selectedWidgets(id){
      
      this.widgets[id].active = !this.widgets[id].active
    },
  },

  created() {
    this.weatherData = [
      {
        time: '12:00',
        temperature: 19,
      },
      {
        time: '13:00',
        temperature: 20,
      },
      {
        time: '14:00',
        temperature: 22,
      },
      {
        time: '15:00',
        temperature: 21,
      }
    ]
    this.widgets =[
      {
        id: '0',
        name: 'Temperaturmåler',
        desc: 'Dette er en temperaturmåler',
        img: 'Bilde',
        active: false,
      },
      {
        id: '1',
        name: 'Fuktighetsmåler',
        desc: 'Dette er en fukighetsmåler',
        img: 'Bilde',
        active: false,
      },
    ]
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

.settingsWindow {
  width: 76%;
  height: 70%;
  position: fixed;
  border: 1px solid #132559;
  border-radius: 5px;
  top: 170px;
  margin-left: 195px;

}
</style>
