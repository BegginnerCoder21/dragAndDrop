<template>
    <div class="home">
        <h1>
            Glisser-Deposer
        </h1>
        <Dropzone @drop.prevent="drop" @change="selectedFile" />
        <span>
            File: {{ dropzoneFiles.name }}
        </span>
    </div>
</template>

<script setup>
import { ref } from 'vue';
import Dropzone from '../dropzone/dropzone.vue';

const dropzoneFiles = ref('');


const drop = (e) =>  {
    dropzoneFiles.value = e.dataTransfer.files[0];
}

const selectedFile = (e) =>{
    dropzoneFiles.value = e.srcElement.files[0];
    // dropzoneFiles.value = document.querySelector(".dropzoneFile").files[0];

}

</script>

<style  scoped>

.home{

    height: 100vh;
    justify-content: center;
    display: flex;
    flex-direction: column;
    align-items: center;
}

h1{
    margin-bottom: 32px;
    font-size: 40px;
}

span{
    margin-top: 32px;
}

</style>