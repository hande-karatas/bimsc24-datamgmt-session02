<!-- the script is where the js code goes -->
<script setup>
import { ref } from "vue" // you need this to use ref()
let name = ref("Hande Karataş")
let course = ref("Data Management")


let count = ref(0)
function increment() {
    count.value += 4
}


function resetCount() {
    count.value = 0;
}


let text = ref("");
let inputText = ref("");
function addText() {
    text.value += inputText.value;
}
function resetText() {
    text.value = ""
}



let Selector = ref("");
let inputcolor = ref("");
function changebgcolor() {
    let element = document.querySelectorAll(Selector.value);
    element.forEach(element => {
        element.style.backgroundColor = inputcolor.value;
    });
}

</script>



<!-- the template is where the html code goes -->
<template>
    <div id="navbar" class="container">
        <div id="title">This website is made by {{ name }} for the {{ course }} seminar.</div>

        <!-- <div id="logo">
            <img src="cow.jpg" alt="macad cow">

        </div> -->


    </div>

    <div id="flex">

        <div id="sidebar" class="container"> Sidebar
            <br>
            <button @click="increment">Count is: {{ count }}</button>
            <button @click="resetCount">Reset number</button>
            <br>
            <br>
            <!--creating new text -->
            <input v-model="inputText" type="text" placeholder="Type anything..." />
            <br>
            <button @click="addText"> Add text </button>
            <br>
            <br>
            <input v-model="Selector" type="text" placeholder="type: #navbar / #sidebar / #main" />
            <br>
            <input v-model="inputcolor" type="text" placeholder="Color" />
            <br>
            <button @click="changebgcolor">Apply Background Color</button>
        </div>

        <div id="main" class="container"> Here is your text:
            <br>


            <p> {{ text }} </p>
            <br> <button @click="resetText">Reset text?</button>
        </div>
    </div>
</template>



<!-- style is where the css code goes -->
<style scoped>
html {

    background-color: rgb(76, 68, 192);
    color: rgb(44, 30, 30);
}

body {

    margin: 0;
}

div {

    /* put the borders in the inside of container */
    box-sizing: border-box;
    border-color: rgb(64, 134, 168);
}

img {

    height: 100%;
    width: auto;

}

#navbar {

    height: 50px;



}



#flex {

    display: flex;
    height: calc(100vh - 50px);
}

#sidebar {

    width: 30%;


}

#main {
    width: 70%;


}

#title {
    width: 70%;
    float: right;
    text-align: right;
}


.container {

    border-style: dotted;
    border-width: 1px;

}
</style>