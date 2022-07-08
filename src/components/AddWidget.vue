<template>
    <div class = "addWidget">
        <h1>Legg til måler</h1>
        <table>
            <thead>
                <tr class="trHead">
                    <th>Måler</th><th>Beskrivelse</th><th>Bilde</th>
                </tr>
            </thead>
            <tbody :key="widget.id" v-for="widget in widgets">
                <tr 
                class="trBody" 
                @click ="$emit('widget-toggle', widget.id)" 
                >
                    <td id = "name">{{ widget.name }}</td>
                    <td id = "desc">{{ widget.desc }}</td>
                    <td id = "img">{{ widget.img }}</td>
                </tr>
            </tbody>
            <tr class="trLast"><td>s</td><td></td><td></td></tr>
        </table>
    </div>
    
</template>

<script>

export default{
    name: 'AddWidget',
    emites: ['selected-widgets'],
    props: {
        widgets: Array,
    }
}
</script>

<style scoped>
h1{
    padding: 5px;
    text-align: center;
}
table{
    font-size:1em;
    margin-left: 5px;
    padding: 5px;
    width: 60rem;
    border-collapse: collapse;
    height:auto;
    border-radius: 5px;
    background-color:#363540;
    color: white;
}
tr{
    height: 60px;
}
#name{
    width:200px;
}
#desc{
    width: 300px;
    font-size: 0.5em;
}
#img{
    max-width:200px;
}
.trHead{
    height: 20px;
}
thead tr th{
    text-align: left;
}
.trBody:hover{
    background-color: #0439D9;
}
.trLast{
    height: 1px;
    color: #363540 
}



</style>

