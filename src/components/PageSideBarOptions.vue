<template>
    <div>
        <h3 @click="emit$('toggle-show', id)"> {{ option }} </h3>
    </div>
</template>

<script>

export default{
    name: 'SideBarOption',
    props: {
        option: String,
        id: Number,
    }
}
</script>
