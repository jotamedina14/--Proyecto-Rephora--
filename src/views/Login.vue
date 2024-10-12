<script setup>
import { ref } from "vue";
import logosena from '../assets/img/logosena.png';

const email = ref('');
const password = ref('');
const role = ref('');
const emailError = ref('');
const passwordError = ref('');
const passwordVisible = ref(false);

const login = () => {
  if (role.value === 'administrador') {
    // Lógica para administrador
  } else if (role.value === 'consultor') {
    // Lógica para consultor
  } else if (role.value === 'instructor') {
    // Lógica para instructor
  } else {
    // Manejar error de rol no seleccionado
  }
};

const forgotPassword = () => {
  // Lógica para olvidar contraseña
};
</script>

<template>
  <div class="login-container">
    <q-layout view="lHh Lpr lFf">
      <q-page-container>
        <q-page class="flex flex-center bg-login">
          <q-card class="q-pa-md shadow-2 my_card" bordered>
            <!-- Sección del logo y el título Login -->
            <q-card-section class="headerLogin text-center">
              <img :src="logosena" alt="Logo SENA" class="imgSena">
              <q-typography tag="h2" class="q-mt-md login-title">Login</q-typography>
            </q-card-section>

            <!-- Reorganizamos los campos, Rol va de primero -->
            <q-card-section>
              <q-select
                dense
                label-color="green-7"
                color="green-4"
                outlined
                class="input"
                v-model="role"
                :options="['administrador', 'consultor', 'instructor']"
                label="Rol">
              </q-select>

              <q-input 
                dense 
                label-color="green-7" 
                color="#38803a" 
                outlined 
                class="q-mt-md input" 
                v-model="email"
                :error="!!emailError" 
                :error-message="emailError" 
                label="Email">
              </q-input>

              <q-input 
                dense 
                label-color="green-7" 
                color="#38803a" 
                outlined 
                class="q-mt-xs input" 
                v-model="password" 
                :type="passwordVisible ? 'text' : 'password'" 
                :error="!!passwordError" 
                :error-message="passwordError" 
                label="Password">
                <template v-slot:append>
                  <q-icon :name="passwordVisible ? 'visibility' : 'visibility_off'"
                          class="cursor-pointer" 
                          @click="passwordVisible = !passwordVisible"/>
                </template>
              </q-input>
            </q-card-section>

            <!-- Olvidar contraseña -->
            <q-card-section class="forgot-password text-center q-my-sm">
              <q-btn flat color="#38803a" label="¿Olvidaste tu contraseña?" @click="forgotPassword()"></q-btn>
            </q-card-section>

            <!-- Botón de Login -->
            <q-card-section>
              <q-btn
                style="border-radius: 12px;" 
                color="#38803a" 
                rounded 
                size="md" 
                label="Iniciar Sesión" 
                no-caps 
                class="full-width btn-login" 
                @click="login()"
                required>
              </q-btn>
            </q-card-section>
          </q-card>
        </q-page>
      </q-page-container>
    </q-layout>
  </div>
</template>

<style scoped>
.bg-login {
  background-color: transparent;
}

.headerLogin {
  display: flex;
  flex-direction: column; /* Cambiar a columna para colocar el texto Login debajo */
  align-items: center;
  justify-content: center;
  position: relative;
}

.imgSena {
  max-width: 100px;
  margin: 10px 0;
}

.login-title {
  font-family: 'Poppins', sans-serif; /* Fuente personalizada */
  color: #38803a; /* Color verde para combinar con el tema */
  font-weight: bold;
  font-size: 1.8rem;
}

.my_card {
  width: 28rem;
  border-radius: 18px;
  background-color: white;
  transition: all 0.4s ease;
  box-shadow: 0 15px 25px rgba(0, 0, 0, 0.1);
}

.my_card:hover {
  transform: translateY(-10px);
  box-shadow: 0 25px 50px rgba(0, 0, 0, 0.2);
}

.input {
  margin-bottom: 12px; /* Ajustamos el espacio entre los inputs */
}

.q-mt-md {
  margin-top: 16px; /* Ajustamos el margen superior para bajar el campo de email */
}

.q-mt-xs {
  margin-top: 4px; /* Ajustamos el margen superior para subir el campo de password */
}

.input:focus {
  border-color: #38803a;
  box-shadow: 0 0 2px #38803a;
}

.cursor-pointer {
  cursor: pointer;
  transition: 0.3s;
}

.cursor-pointer:hover {
  color: #38803a;
}

.forgot-password {
  font-size: 0.9rem;
  font-weight: bold;
  color: #38803a;
  transition: 0.3s;
}

.forgot-password:hover {
  color: #38803a;
}

.btn-login {
  background: linear-gradient(45deg, #38803a, #38803a);
  color: white;
  font-weight: bold;
  transition: background 0.3s ease;
}

.btn-login:hover {
  background: linear-gradient(45deg, #38803a, #38803a);
  transform: translateY(-3px);
  box-shadow: 0 10px 20px rgba(67, 160, 71, 0.4);
}
</style>