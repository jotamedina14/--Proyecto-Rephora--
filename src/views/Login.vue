<script setup>
import { onBeforeMount, ref } from "vue";
import axios from "axios";
import { useQuasar } from "quasar";
import iconSena from "../assets/icon.png";
import logosena from '../assets/img/logosena.png';	

</script>

<template>
  <div class="login-container">
      <q-layout view="lHh Lpr lFf">
          <q-page-container>
              <q-page class="flex flex-center bg-login">
                  <q-card class="q-pa-md shadow-2 my_card" bordered>
                      <q-card-section class="headerLogin text-center">
                          <img :src="logosena" alt="Logo SENA" class="imgSena">
                      </q-card-section>
                      <q-card-section>
                          <q-input 
                              dense 
                              label-color="green-7" 
                              color="green-4" 
                              outlined 
                              class="input" 
                              v-model="email"
                              :error="!!emailError" 
                              :error-message="emailError" 
                              label="Email">
                          </q-input>
                          <q-input 
                              dense 
                              label-color="green-7" 
                              color="green-4" 
                              outlined 
                              class="q-mt-md input" 
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
                      <q-card-section class="forgot-password text-center q-my-sm">
                          <q-btn flat color="green-6" label="¿Olvidaste tu contraseña?" @click="forgotPassword()"></q-btn>
                      </q-card-section>
                      <q-card-section>
                          <q-btn
                                 style="border-radius: 12px;" 
                                 color="green" 
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
  flex-direction: row;
  align-items: center;
  justify-content: center;
  position: relative;
}

.imgSena {
  max-width: 100px;
  margin: 10px 0;
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

.input:focus {
  border-color: #66bb6a;
  box-shadow: 0 0 2px #66bb6a;
}

.cursor-pointer {
  cursor: pointer;
  transition: 0.3s;
}

.cursor-pointer:hover {
  color: #66bb6a;
}

.forgot-password {
  font-size: 0.9rem;
  font-weight: bold;
  color: #66bb6a;
  transition: 0.3s;
}

.forgot-password:hover {
  color: #43a047;
}

.btn-login {
  background: linear-gradient(45deg, #43a047, #66bb6a);
  color: white;
  font-weight: bold;
  transition: background 0.3s ease;
}

.btn-login:hover {
  background: linear-gradient(45deg, #2e7d32, #43a047);
  transform: translateY(-3px);
  box-shadow: 0 10px 20px rgba(67, 160, 71, 0.4);
}
</style>