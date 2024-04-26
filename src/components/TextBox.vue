<template>
    <div class="title-box">
        <h1>
            Bem-vido ao<br>Tutilabs
            <img class="waving" src="../assets/HandWaving.svg" alt="hand waving">
        </h1>
        
        <img class="plush" src="../assets/Mask group.svg" alt="plush unicorn">
        
    </div>
    <div>
        <p>
            Olá,
            Agradecemos seu interesse em estagiar na Tutiplast e por participar do nosso teste de front-end. Este
            teste<br>
            foi desenvolvido para avaliar suas habilidades e conhecimentos na área, portanto, não se preocupe se não<br>
            conseguir completar todas as tarefas. O objetivo é entender seu processo de resolução de problemas e seu<br>
            conhecimento técnico.
        </p>
    </div>
</template>

<script>
export default {
    name: 'AppText',
}
</script>

<style scoped>.title-box {
    display: flex;
    justify-content: space-between;
    align-items: center; 
    width: 80%;
    margin: 2% auto;
}

h1 {
    color: #424242;
    font-size: 4vw;
    font-weight: 700;
}

.plush {
    background-color: #feab5e;
    border-radius: 25px;
    height: fit-content;
    width: 60%;
    height: 40%;
    margin-left: 2rem;
}
@keyframes wave-animation {
    0% { transform: rotate(0.0deg); }
    10% { transform: rotate(14.0deg); }
    20% { transform: rotate(-8.0deg); }
    30% { transform: rotate(14.0deg); }
    40% { transform: rotate(-4.0deg); }
    50% { transform: rotate(10.0deg); }
    60% { transform: rotate(0.0deg); }
    100% { transform: rotate(0.0deg); }
}

.waving {
    animation-name: wave-animation;
    animation-duration: 2.5s;
    animation-iteration-count: infinite;
    transform-origin: 70% 70%; /* Ajuste este valor conforme necessário */
    display: inline-block;
   }
   
</style>