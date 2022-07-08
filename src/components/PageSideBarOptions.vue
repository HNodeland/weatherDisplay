<template>
    <div>
        <h3> {{ option }} </h3>
    </div>
</template>

<script>

export default{
    name: 'SideBarOption',
    props: {
        option: String,
        
    }
}
</script>
