<template>
    <div class="container">
        <div class="texts">
            <span>
                Bem-vido ao<br>Tutilabs
                <img class="waving" src="../assets/HandWaving.svg" alt="hand waving">
            </span>

            <p>
                Olá,<br>
                Agradecemos seu interesse em estagiar na Tutiplast e por participar do nosso teste de 
                front-end. Este teste foi desenvolvido para avaliar suas habilidades e conhecimentos na 
                área, portanto, não se preocupe se não conseguir completar todas as tarefas. O objetivo é 
                entender seu processo de resolução de problemas e seu conhecimento técnico.
            </p>
        </div>

        <div class="image-container">
            <img class="unicorn-image desktop-image" src="../assets/Mask group.svg" alt="plush unicorn">
            <img class="unicorn-image mobile-image" src="../assets/Mask group_.png" alt="plush unicorn">
        </div>
    </div>
</template>

<script>
export default {
    name: 'AppNavbar',
}
</script>

<style> 
.container {
    display: flex;
    flex-direction: column;
    width: 80%;
    margin: 3% auto;
}

span {
    color: #424242;
    font-size: 4.6vw;
    white-space: nowrap;
    font-weight: 500;
}

p {
    font-family: Poppins;
    font-size: 11px;
    font-weight: 400;
    line-height: 16.1px;
    color: black;
    text-align: justify;
    font-size: 0.9rem;
}

.image-container {
    background-color: #feab5e;
    border-radius: 25px;
    width: 46vw;
    height: 20vw;
    margin-left: 3.9rem;
    display: flex;
    justify-content: end;
}
.unicorn-image {
    border-radius: 25px;
    width: 50vw;
    height: 20vw;
}

@keyframes wave-animation {
    0% {
        transform: rotate(0.0deg);
    }

    10% {
        transform: rotate(14.0deg);
    }

    20% {
        transform: rotate(-8.0deg);
    }

    30% {
        transform: rotate(14.0deg);
    }

    40% {
        transform: rotate(-4.0deg);
    }

    50% {
        transform: rotate(10.0deg);
    }

    60% {
        transform: rotate(0.0deg);
    }

    100% {
        transform: rotate(0.0deg);
    }
}

.waving {
    animation-name: wave-animation;
    animation-duration: 2.5s;
    animation-iteration-count: infinite;
    transform-origin: 70% 70%;
    display: inline-block;
}

.desktop-image {
    display: block;
   }
   
.mobile-image {
    display: none;
}

@media (min-width: 600px) {
    .container {
        flex-direction: row;
    }

}

@media (max-width: 600px) {
    .container {
        flex-direction: column;
        margin: 5% auto;
        width: 93%;
    }

    .image-container {
        width: 95vw; 
        height: 75vw;
        margin-left: -1.2%;
        margin-top: 6%;
    }

    .unicorn-image {
        width: 95.8vw;
        height: 75vw;
        border-radius: 30px;
    }

    span {
        color: #424242;
        font-size: 2.2rem;
    }
    .waving{
        width: 44px;
        font-family: Poppins;
        font-size: 1rem;
        font-weight: 500;
    }

    .paragraph{
        font-size: 0.6rem;
        margin-top: 1%;    
    }

    .desktop-image {
            display: none;
    }

    .mobile-image {
        display: block;
    }
}

</style>