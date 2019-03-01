<template>
    <div class="header">
        This is just a demo header !
        <span class="author">
            {{ author }}
        </span>
    </div>
</template>

<script>
export default {
    name: 'header',
    props: {
        author: String
    }
}
</script>

<style scoped>
.header {
    position: fixed;
    left: 0;
    top: 0;
    width: 100%;
    background-color: grey;
    color: white;
    text-align: center;
}
</style>


