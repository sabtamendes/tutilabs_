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
    height: auto; 
    display: flex;
    justify-content: space-between;
    align-items: center;
    box-sizing: border-box;
    padding: 15px;
    margin: 0 auto;
    position: relative;
    top: 2%;
}

a {
    color: inherit;
}

.btn {
    background-color: #C3C3C3;
    padding: 0.54em 0.625em; 
    border-radius: 0.24em;
    display: inline-block;
    transition: background-color 0.3s ease;
}

@media (max-width: 768px) {
    header {
        width: 95%; 
    }

    .btn {
        padding: 0.5em 0.75em; 
        border-radius: 0.2em; 
    }
}

@media (max-width: 425px) {
    header {
        width: 95%; 
    }

    .btn {
        padding: 0.8em 0.75em; 
        border-radius: 0.2em; 
    }

    a {
        color: inherit;
        font-size: 12px;
    }
}
</style>
