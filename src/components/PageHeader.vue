<template>
    <header>
        <h1>{{ title }}
        <i @click="$emit('toggle-menu')"  class="fas fa-thin fa-gear menu"></i>
        </h1>
    </header>
</template>

<script>
export default{
    name: 'PageHeader',
    props: {
        title: {
            type: String,
            default: "Could not fetch text data",
        },
    },
    components:{

    }
}

</script>

<style scoped>

.menu {
    float: right;
    padding: 7px;
    border-radius: 20%;
    border: 1px solid #142559;
    transition: ease-out .15s;
    box-shadow: inset 0 0 0 0 #0439D9;
}
.menu:hover{
    border-width: 2px;
 
}
</style>