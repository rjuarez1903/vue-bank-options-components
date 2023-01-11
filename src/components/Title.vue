<template>
    <div class="title">
        <h1>{{ text }}</h1>
    </div>
</template>

<script>
export default{
    name: 'Title',
    props: {
        text: String
    }
}
</script>

<style scoped>
    h1 {
        color: #42B883;        
    }
</style>  