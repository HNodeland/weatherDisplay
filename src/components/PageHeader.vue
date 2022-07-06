<template>
    <header>
        <h1>{{ title }}
        <i class="fas fa-bars menu"></i>
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
}
.menu:hover{
    
    border-color: #325CD9;
    border-width: 4px;
}
</style>