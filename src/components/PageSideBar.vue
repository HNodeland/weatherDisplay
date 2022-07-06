<template>
    <div class = "sidebar">
        <SideBarOption @click="$emit('toggle-widget')" class = "sideBarOption" option = "Legg til"/>
        <SideBarOption @click="$emit('toggle-setup')" class = "sideBarOption" option = "Oppsett"/>
        <SideBarOption @click="$emit('toggle-settings')" class = "sideBarOption" option = "Instillinger"/>        
    </div>
</template>

<script>
import SideBarOption from './PageSideBarOptions'

export default{
    name: 'SideBar',
    components: {
        SideBarOption,

    }
}
</script>

<style scoped>
.sideBarOption{
    margin: 2px;
    padding-top: 27px;
    text-align: center;
    background-color: #363540;
    color: #ffffff;
    width: 250px;
    height: 100px;
    border: none;
    border-radius: 4px;
    box-shadow: inset 0 0 0 0 #0439D9;
    transition: ease-out 0.15s;
    font-size: 1.5rem;
}
.sideBarOption:hover{
    box-shadow: inset 250px 0 0 0 #0439D9;
}



</style>
