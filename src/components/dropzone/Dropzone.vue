<template>
        <div class="dropzone"
        @dragover.prevent
        @dragenter.prevent="toggleActive"
        @dragleave.prevent="toggleActive"
        @drop.prevent="toggleActive"
        :class="{'active-dropzone' : Active}"
        >
            <span>
                Glisser-deposer un fichier
            </span>
            <span>
                OU
            </span>
            <label id="label" for="dropzoneFile">Selectionnez un fichier</label>
            <input type="file" id="dropzoneFile" class="dropzoneFile"> 
        </div>
</template>

<script setup>
import { ref } from 'vue';


const Active = ref(false);

const toggleActive = () =>  {
    Active.value = !Active.value;
}

</script>

<style scoped>

.dropzone{
    width: 400px;
    height: 200px;
    row-gap: 16px;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #fff;
    transition: .3s ease all;
    flex-direction: column;
    border: 2px dashed #41b883;
}

label{
    padding: 8px 12px;
    background-color: #41b883;
    color: #fff;
    transition: .3s ease all;

}

input{
    display: none;
}

.active-dropzone{
    background-color: #41b883;
    border-color: #fff;
    color: #fff;

      #label {
        background-color: #fff;
        color: #41b883;
    }
    
}

</style>