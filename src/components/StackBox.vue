<template>
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

    <div class="toolbar">
        <div class="stacks" v-show="activeButton === 'front-end'">
            <div class="button-arrow left" :class="{ 'hidden': currentIndex === 0 }" @click="navigateLeft">
                <img src="../assets/images/arrow-right.png" alt="Arrow Left">
            </div>
            <div class="row-stack">
                <div class="stack" @click="selectStack('SASS')">
                    <img src="../assets/images/sass.png" alt="SASS">
                </div>
                <div class="stack" @click="selectStack('VUE')">
                    <img src="../assets/images/vue.png" alt="VUE">
                </div>
                <div class="stack" @click="selectStack('TYPESCRIPT')">
                    <img src="../assets/images/ts.png" alt="Typescript">
                </div>
                <div class="stack" @click="selectStack('GITHUB')">
                    <img src="../assets/images/github.png" alt="Github">
                </div>
                <div class="stack" @click="selectStack('HTML')">
                    <img src="../assets/images/html.png" alt="HTML">
                </div>
                <div class="stack" @click="selectStack('JAVASCRIPT')">
                    <img src="../assets/images/js.png" alt="Javascript">
                </div>
                <div class="stack" @click="selectStack('CSS')">
                    <img src="../assets/images/css.png" alt="CSS">
                </div>
            </div>
            <div class="button-arrow right" :class="{ 'hidden': currentIndex + itemsPerPage >= stacks.length }"
                @click="navigateRight">
                <img src="../assets/images/arrow-left.png" alt="Arrow Right">
            </div>
        </div>

        <div class="stacks" v-show="activeButton === 'back-end'">
            <div class="button-arrow left" :class="{ 'hidden': currentIndex === 0 }" @click="navigateLeft">
                <img src="../assets/images/arrow-left.png" alt="Arrow Left">
            </div>
            <div class="row-stack">
                <div class="stack" @click="selectStack('MYSQL')">
                    <img src="../assets/images/mysql.png" alt="MYSQL">
                </div>
                <div class="stack" @click="selectStack('PRISMA')">
                    <img src="../assets/images/prisma.png" alt="PRISMA">
                </div>
                <div class="stack" @click="selectStack('TYPESCRIPT')">
                    <img src="../assets/images/ts.png" alt="Typescript">
                </div>
                <div class="stack" @click="selectStack('GITHUB')">
                    <img src="../assets/images/tigre.png" alt="Github">
                </div>
                <div class="stack" @click="selectStack('NODE')">
                    <img src="../assets/images/node.png" alt="NODE">
                </div>
            </div>
            <div class="button-arrow right" :class="{ 'hidden': currentIndex + itemsPerPage >= stacks.length }"
                @click="navigateRight">
                <img src="../assets/images/arrow-left.png" alt="Arrow Right">
            </div>
        </div>

        <div class="text-box" v-show="showTextBox">
            <h2>{{ selectedStack }}</h2>
            <hr>
            <p>Lorem ipsum dolor sit amet consectetur. Est ac tristique congue at nunc. Urna ullamcorper tortor blandit
                at interdum eget. Ut ipsum ut dolor dolor diam in. Pharetra sit ultrices vitae turpis augue tempor.
            </p>
            <p>Lorem ipsum dolor sit amet consectetur. Est ac tristique congue at nunc. Urna ullamcorper tortor blandit
                at interdum eget. Ut ipsum ut dolor dolor diam in. Pharetra sit ultrices vitae turpis augue tempor.
            </p>
            <p>Lorem ipsum dolor sit amet consectetur. Est ac tristique congue at nunc. Urna ullamcorper tortor blandit
                at interdum eget. Ut ipsum ut dolor dolor diam in. Pharetra sit ultrices vitae turpis augue tempor.
            </p>
        </div>

        <div v-show="showOverlay">
            <b-overlay :show="show" rounded="sm">
                <div class="image-container">
                    <img src="../assets/images/Mask group.png" alt="Imagem de fundo">
                    <div class="overlay-content">
                        <b-card title="Card com sobreposição" :aria-hidden="show ? 'true' : null">
                            <b-card-text>Veja mais sobre nosso sistema</b-card-text>
                        </b-card>
                    </div>
                </div>
            </b-overlay>
            <span class="button-overlay">Visualizar <img src="../assets/images/arrow.png" alt=""></span>
        </div>
    </div>
</template>

<script>
export default {
    name: 'AppStacks',
    data() {
        return {
            showTextBox: false,
            showOverlay: false,
            selectedStack: '',
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
            console.log(stackName);

            this.selectedStack = stackName;
            this.showTextBox = true;
            this.showOverlay = true;
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
.test-box {
    width: 15%;
    margin-top: -5%;
    margin-left: 10%;
    align-items: flex-start;
}

.test-box h6 {
    font-family: Poppins;
    font-size: 12.4px;
    font-weight: 700;
    line-height: 13.64px;
    text-align: left;
    margin-bottom: 5%;
}

.buttons {
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

.button-arrow.right img{
    background-color: #d9d9d9;
    padding-bottom: 7%;
}

.button-arrow.left img{
    background-color: #d9d9d9;
}

.stacks {
    display: flex;
    justify-content: space-between;
    width: 32vw; 
    height: 8.25rem; 
    border-radius: 4.25rem; 
    background: #D9D9D9;
    overflow-x: hidden;
    -ms-overflow-style: none;
    scrollbar-width: none;
    padding: 0.3125rem; 
    padding-right: 0; 
    margin-right: 3.125rem;
}

.row-stack {
    display: flex;
    flex-wrap: nowrap;
    transition: transform 0.3s ease-in-out;
    width: 6.25rem; 
    height: 6.25rem; 
    padding-bottom: 0%;
}

.stack {
    flex: 0 0 auto;
    margin-right: 0.625rem; 
    cursor: pointer;
}

.stack img {
    width: 7.5rem; 
    height: 7.5rem; 
    border-radius: 3.75rem; 
}

.stacks::-webkit-scrollbar {
    display: none;
}

.hidden {
    display: none;
}

.button-arrow {
    cursor: pointer;
}

.text-box {
    background-color: #ececec;
    color: #000000;
    width: 20vw;
    max-width: 480px; 
    height: 19.6rem; 
    padding: 1.25rem; 
    border-radius: 1.5625rem; 
    border: 0.0625rem solid black; 
    font-family: Poppins;
    overflow: auto;
    margin-right: 2%;
}

.text-box h2 {
    font-family: Poppins;
    font-size: 0.9375rem; 
    font-weight: 700;
    line-height: 1.5rem; 
    text-align: left;
}

.text-box p {
    font-family: Poppins;
    font-size: 0.75rem;
    font-weight: 400;
    line-height: 0.8125rem;
    text-align: left;
    margin-top: 4.5%;
}

hr {
    border: none;
    height: 0.0625rem;
    background-color: #000000;
    margin-top: 0.625rem; 
    margin-bottom: 0.625rem; 
}

.image-container {
    position: relative;
    width: 300px;
    height: 313px;
    background-color: #4c577d;
    border-radius: 20px;
}

.image-container img {
    width: fit-content;
    height: 98%;
    object-fit: cover;
}

.overlay-content {
    position: absolute;
    bottom: 0;
    left: 2%;
    top: 69%;
    width: 96%;
    height: 30%;
    display: flex;
    justify-content: center;
    background-color: rgba(245, 245, 245, 0.5);
    backdrop-filter: blur(10px);
    text-align: top;
    font-size: 14px;
    border-radius: 18px;
    opacity: 10;
    padding: 6%;
}

.button-overlay {
    cursor: pointer;
    position: absolute;
    top: 83%;
    left: 90%;
    background-color: #4c577d;
    border-radius: 20px;
    width: 9%;
    height: 10%;
    display: flex;
    justify-content: space-between;
    padding-left: 15px;
    padding-right: 15px;
    align-items: center;
    color: white;
    font-family: Poppins;
    font-size: 12.4px;
    font-weight: 400;
    line-height: 13.64px;
    text-align: left;
}

.toolbar {
    display: flex;
    justify-content: space-between;
    width: 80%;
    margin-top: 1.5%;
    position: relative;
    left: 9.7%;
}

@media (max-width: 600px) {
    .test-box {
        width: 60%;
        margin-top: -1%;
        margin-left: 3.5%;
        align-items: flex-start;
    }
    .toolbar {
        display: flex;
        justify-content: center;
        flex-direction: column;
        width: 80rem;
        margin-top: 3%;
        position: relative;
        left: -0.2%;
    }
    .stack {
        flex: 0 0 auto;
        margin-right: 0.8rem; 
        cursor: pointer;
        padding-bottom: 0%;
        height: 0%;
    }
  
    .stacks {
        width: 25.5rem; 
        height: 5.7rem; 
        border-radius: 4.25rem; 
        background: #D9D9D9;
        overflow-x: hidden;
        -ms-overflow-style: none;
        scrollbar-width: none;
        padding-bottom: 0%;
        margin-left: 1%;
    }

    .row-stack {
        display: flex;
        flex-wrap: nowrap;
        transition: transform 0.3s ease-in-out;
        padding: 0%;
    }
    
    .stack img {
        width: 19vw;
        height: fit-content;
    }

    .button-arrow.right img{
        width: 17vw;
    }
        
    .button-arrow.left img{
        width: 17vw;
    }

    .text-box {
        width: 25.5rem;
        margin-top: 2%;
        margin-left: 1.2%;
        margin-bottom: -3%;
    }

    .image-container {
        margin-left: 1.2%;
        width: 25rem;
    }

    .image-container img {
        margin-left: 1.2%;
        width: 25rem;
    }

    .button-overlay {
        position: absolute;
        top: 94%;
        left: 21.5%;
        width: 10%;
        height: 5%;
    }
}
</style>