<template>
    <div class="title-box">
        <h1>
            Bem-vido ao<br>Tutilabs
            <img class="waving" src="../assets/HandWaving.svg" alt="hand waving">
        </h1>

        <img class="plush" src="../assets/Mask group.svg" alt="plush unicorn">

    </div>
    <div class="paragraph">
        <p>
            Olá,<br>
            Agradecemos seu interesse em estagiar na Tutiplast e por participar do nosso teste de <br>
            front-end. Este teste foi desenvolvido para avaliar suas habilidades e conhecimentos na <br>
            área, portanto, não se preocupe se não conseguir completar todas as tarefas. O objetivo é <br>
            entender seu processo de resolução de problemas e seu conhecimento técnico.
        </p>
    </div>

    <div class="test-box">
        <h6>Tipo de teste</h6>
        <div class="buttons">
            <span :class="activeButton === 'front-end' ? 'button-active' : 'button-inactive'"
                @click="toggleButton('front-end')">
                front-end <img :src="activeButton === 'front-end' ? '../assets/happyface.svg' : '../assets/sadface.svg'"
                    alt="">
            </span>
            <span :class="activeButton === 'back-end' ? 'button-active' : 'button-inactive'"
                @click="toggleButton('back-end')">
                back-end <img :src="activeButton === 'back-end' ? '../assets/happyface.svg' : '../assets/sadface.svg'"
                    alt="">
            </span>
        </div>
    </div>

    <div class="stacks" v-show="activeButton === 'front-end'">
        <div class="button-arrow" :class="{ 'hidden': currentIndex === 0 }" @click="navigateLeft">
            <img src="../assets/images/arrow-left.png" alt="Arrow Left">
        </div>
        <div class="row-stack">
            <div class="stack stack-front pink" @click="selectStack('SASS')">
                <img src="../assets/images/sass.png" alt="SASS">
            </div>
            <div class="stack stack-front green" @click="selectStack('VUE')">
                <img src="../assets/images/vue.png" alt="VUE">
            </div>
            <div class="stack stack-front blue" @click="selectStack('Typescript')">
                <img src="../assets/images/ts.png" alt="Typescript">
            </div>
            <div class="stack stack-front white" @click="selectStack('Github')">
                <img src="../assets/images/github.png" alt="GIthub">
            </div>
            <div class="stack stack-front orange" @click="selectStack('HTML')">
                <img src="../assets/images/html.png" alt="HTML">
            </div>
            <div class="stack stack-front yellow" @click="selectStack('Javascript')">
                <img src="../assets/images/js.png" alt="Javascript">
            </div>
            <div class="stack stack-front blue" @click="selectStack('CSS')">
                <img src="../assets/images/css.png" alt="CSS">
            </div>
        </div>
        <div class="button-arrow" :class="{ 'hidden': currentIndex + itemsPerPage >= stacks.length }"
            @click="navigateRight">
            <img src="../assets/images/arrow-right.png" alt="Arrow Right">
        </div>
    </div>


</template>

<script>
export default {
 name: 'AppText',
 data() {
    return {
      activeButton: 'front-end',
      currentIndex: 0,
      itemsPerPage: 3,
      stacks: [
            { name: 'SASS', image: '../assets/images/sass.png' },
            { name: 'VUE', image: '../assets/images/vue.png' },
            { name: 'Typescript', image: '../assets/images/ts.png' },
            { name: 'Github', image: '../assets/images/github.png' },
            { name: 'HTML', image: '../assets/images/html.png' },
            { name: 'Javascript', image: '../assets/images/js.png' },
            { name: 'CSS', image: '../assets/images/css.png' },
        ]
    };
 },
 methods: {
    toggleButton(button) {
      this.activeButton = button;
    },
    selectStack(stackName) {
      console.log(`Stack selecionado: ${stackName}`);
    },

     navigateLeft() {
         if (this.currentIndex > 0) {
             this.currentIndex -= this.itemsPerPage;
         }
     },
     navigateRight() {
         if (this.currentIndex + this.itemsPerPage < this.stacks.length) {
             this.currentIndex += this.itemsPerPage;
         }
     },
 },
 computed: {
    visibleStacks() {
        return this.stacks.slice(this.currentIndex, this.currentIndex + this.itemsPerPage);
    },
},

};
</script>


<style scoped>
.title-box {
    display: flex;
    justify-content: space-between;
    width: 80%;
    margin: 2% auto;
}

h1 {
    color: #424242;
    font-size: 4vw;
    margin-top: 0%;
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
    transform-origin: 70% 70%;
    display: inline-block;
   }

.paragraph {
    font-family: Poppins;
    font-size: 11px;
    font-weight: 400;
    line-height: 12.1px;
    text-align: justified;
    width: 38%;
    margin-top: -11%;
    margin-left: 10%;
}

.paragraph p {
    color: black;
    text-align: justify;
    font-size: 0.7rem;
}

.test-box {
    width: 15%;
    margin-top: 1%;
    margin-left: 10%;
    align-items: flex-start;
}

.test-box h6{
    font-family: Poppins;
    font-size: 12.4px;
    font-weight: 700;
    line-height: 13.64px;
    text-align: left;
    margin-bottom: 5%;
}

.buttons{
    display: flex;
    justify-content: space-between;
}

.buttons span {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 122.5px;
    height: 40.5px;
    font-family: Poppins;
    font-size: 12.4px;
    font-weight: 400;
    line-height: 13.64px;
    text-align: center;
    padding: 10px 16px 10px 16px;
    border-radius: 24px;
}

.buttons span img {
    border-radius: 50%;
    margin-left: 5px;
}

.button-active {
    background-color: black;
    color: #ffffff;
    cursor: pointer;
}

.button-active::after {
    content: url('../assets/happyface.svg');
}

.button-inactive {
    color: black;
    border: 1px solid black;
    cursor: pointer;
}

.button-inactive::after {
    content: url('../assets/sadface.svg');
}

.stacks {
    display: flex;
    justify-content: space-between;
    width: 504px;
    height: 113px;
    border-radius: 67.57px;
    background: #D9D9D9;
    margin-left: 9.9%;
    margin-top: 2%;
    overflow-x: hidden;
    -ms-overflow-style: none;
    scrollbar-width: none;
    padding: 5px;
    padding-right: 0%;
}


.row-stack {
    display: flex;
    flex-wrap: nowrap;
    transition: transform 0.3s ease-in-out;
    width: 100px;
    height: 100px;
}

.stack {
    flex: 0 0 auto;
    margin-right: 10px;
    cursor: pointer;
}

.stack img {
    width: 100px;
    height: 100px;
    border-radius: 50%;
}

.stacks::-webkit-scrollbar {
    display: none;
}

.hidden {
    display: none;
}

.button-arrow{
    cursor: pointer;
}
</style>