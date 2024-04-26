<template>
    <header>
        <img src="../assets/Tutilabs-logo 3.svg" alt="logo da tutilabs">
        <a class="btn" href="https://linkedin.com/in/bruno-cmarinho">feito por: Bruno marinho</a>
    </header>

</template>

<script>
export default {
    name: 'AppHeader',
}
</script>

<style scoped>
header {
    background-color: #d7d2d2;
    border-radius: 5px;
    width: 80%;
    height: 69px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    box-sizing: border-box;
    padding: 10px;
    margin: 0 auto;
}

a {
    color: inherit;
}

.btn {
    background-color: #C3C3C3;
    padding: 8.59px 10px;
    border-radius: 3.95px;
    display: inline-block;
    transition: background-color 0.3s ease;
}
</style>