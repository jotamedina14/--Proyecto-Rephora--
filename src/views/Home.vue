<script setup>
import { onBeforeMount, ref } from 'vue'
import axios from 'axios'
import { useQuasar } from 'quasar';
import CardComponent from '../components/cards/cardsMenu.vue';

import logImage from '../assets/img/usuarios.png';
import apprenticeImage from '../assets/img/aprendices.png';
import binnacleImage from '../assets/img/bitacoras.png';
import modalityImage from '../assets/img/fichasImage.png';
import followupImage from '../assets/img/seguimientosImage.png';
import assignmentImage from '../assets/img/modalidadImage.png';

</script>

<template>
    <div class="q-pa-xl row items-center justify-center q-gutter-md contenedor">
        <div>
            <CardComponent titles="Log" :imgSrc="logImage" to="/log" />
        </div>
        <div>
            <CardComponent titles="Aprendices" :imgSrc="apprenticeImage" to="/apprentice" />
        </div>
        <div>
            <CardComponent titles="Bitacora" :imgSrc="binnacleImage" to="/binnacle" />
        </div>
        
        <div>
            <CardComponent titles="Modalidad" :imgSrc="modalityImage" to="/modality" />
        </div>
        
        <div>
            <CardComponent titles="Seguimientos" :imgSrc="followupImage" to="/followup" />
        </div>

        <div>
            <CardComponent titles="Asignacion" :imgSrc="assignmentImage" to="/assignment" />
        </div>
    </div>
</template>

<style scoped>

.contenedor {
    padding-top: 25px;
}
</style>