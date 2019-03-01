<template>
    <div class="footer">
        This is just a demo footer !
        <span class="author">
            {{ author }}
        </span>
    </div>
</template>

<script>
export default {
    name: 'footer',
    props: {
        author: String
    }
}
</script>

<style scoped>
.footer {
    position: fixed;
    left: 0;
    bottom: 0;
    width: 100%;
    background-color: grey;
    color: white;
    text-align: center;
}
</style>


