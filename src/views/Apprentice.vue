<script setup>

</script>

<template>

</template>

<style scoped></style>

<!-- examples  -->
<!--

------------ función get -------

<script setup>
import { ref, onMounted } from 'vue';
import { getData } from '@/services/apiClient';

const data = ref(null);
const error = ref(null);
const loading = ref(false);

onMounted(async () => {
  loading.value = true;
  try {
    data.value = await getData('/ruta/datos', { param1: 'value' });
  } catch (err) {
    error.value = err.message;
  } finally {
    loading.value = false;
  }
});
</script>

<template>
  <div v-if="loading">Cargando...</div>
  <div v-else-if="error">{{ error }}</div>
  <div v-else>{{ data }}</div>
</template>


------------ función post -------

<script setup>
import { ref } from 'vue';
import { postData } from '@/services/apiClient';

const formData = ref({
  name: '',
  email: ''
});

const success = ref(false);
const error = ref(null);

const submitForm = async () => {
  try {
    const response = await postData('/ruta/post', formData.value);
    console.log('Respuesta del servidor:', response);
    success.value = true;
  } catch (err) {
    error.value = err.message;
  }
};
</script>

<template>
  <form @submit.prevent="submitForm">
    <input v-model="formData.name" placeholder="Nombre" />
    <input v-model="formData.email" placeholder="Correo" />
    <button type="submit">Enviar</button>
  </form>

  <div v-if="success">¡Formulario enviado con éxito!</div>
  <div v-if="error">{{ error }}</div>
</template>

------------ función put -------

<script setup>
import { ref } from 'vue';
import { putData } from '@/services/apiClient';

const formData = ref({
  name: '',
  email: ''
});

const success = ref(false);
const error = ref(null);

const updateForm = async () => {
  try {
    const response = await putData('/ruta/put/1', formData.value);
    console.log('Actualización exitosa:', response);
    success.value = true;
  } catch (err) {
    error.value = err.message;
  }
};
</script>

<template>
  <form @submit.prevent="updateForm">
    <input v-model="formData.name" placeholder="Nombre" />
    <input v-model="formData.email" placeholder="Correo" />
    <button type="submit">Actualizar</button>
  </form>

  <div v-if="success">¡Actualización exitosa!</div>
  <div v-if="error">{{ error }}</div>
</template>

-->
