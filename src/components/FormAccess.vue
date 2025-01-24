<template>
  <Form
    :validation-schema="validationSchema"
    @submit="onSubmit"
    class=" align-content-end align-items-center  container d-flex flex-column justify-content-center mt-5 gap-4"
    id="formAccess"
  >
    <div class="d-flex flex-column">
      <Field id="email" type="email" name="email" placeholder="Correo" class="fieldChange" />
      <ErrorMessage name="email" class="text-danger fs-8" />
    </div>
    <div class="d-flex flex-column">
      <Field id="passwd" type="password" name="passwd" placeholder="Contraseña" class="fieldChange"/>
      <ErrorMessage name="passwd" class="text-danger" />
    </div>
    <span v-if="errorApi" class="text-danger"
      >Correo electronico o la contraseña no son correctos</span
    >
    <button type="submit" class="btn btn-primary px-3 colorPrimary">Enviar</button>
  </Form>
</template>
    
<script setup>
import { ErrorMessage, Field, Form } from "vee-validate";
import { toTypedSchema } from "@vee-validate/zod";
import { z } from "zod";
import axios from "axios";
import { inject, defineProps } from "vue"; // Necesario para inyectar el método
// import { useRoute } from 'vue-router';

const callIsLogged = inject("callIsLogged");

const props = defineProps({
  apiUrl: {
    type: String,
    required: true,
  },
});

const validationSchema = toTypedSchema(
  z.object({
    email: z
      .string()
      .min(1, "Este campo es obligatorio")
      .email({ message: "Introduce un correo valido" }),
    passwd: z
      .string()
      .min(1, "Este campo es obligatorio")
      .min(6, { message: "La contraseña es demasiado corta" }),
  })
);

function onSubmit(values) {
  // alert(JSON.stringify(values))

  axios
    .post(props.apiUrl, {
      email: values.email,
      password: values.passwd,
    })
    .then(function (response) {
      localStorage.setItem("token", response.data.token);
      window.location.reload();
    })
    .catch(function (error) {
      const errorApi = error;
      return errorApi;
    });
}

if (callIsLogged) {
  callIsLogged();
}
</script>

<style scoped>

.fieldChange{
  border: 0;
    background: #f1f3f5bd;
    border-bottom: 1px solid black;
    width: 30vh;
}

.colorPrimary{
  background-color: #41B883;
  border: none;
  width: 12vh;
}

.colorPrimary:hover{
  background-color: #35495E;

}

</style>