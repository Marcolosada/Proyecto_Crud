<script>
import axios from "axios";
//import slider from '../components/InputSliders.vue';
let API_URL = `/api/guardarPersonasUxd.php`;
export default {
    data() {
        return {
            nombre: "",
            edad: "",
            estadoCivil: "",
            trabajo: "",
            residencia: "",
            cita: "",
            citaAutor: "",
            bio: "",
            personalidad01: "50",
            personalidad02: "50",
            personalidad03: "50",
            personalidad04: "50",
            objetivos: [""],
            frustraciones: [""],
            motivaciones: "",
            porcentaje: "",
            marcas: "",
        };
    },
    methods: {
      Enviar(){
            if(this.validar() ){
                axios.post("/api/guardarPersonasUxd.php", {
                nombre: this.nombre,
                edad: this.edad,
                estadoCivil: this.estadoCivil,
                trabajo: this.trabajo,
                residencia: this.residencia,
                cita: this.cita,
                citaAutor: this.citaAutor,
                bio: this.bio,
                personalidad01: this.personalidad1,
                personalidad02: this.personalidad2,
                personalidad03: this.personalidad3,
                personalidad04: this.personalidad4,
                objetivos: this.objetivos,
                frustraciones: this.frustraciones,
                motivaciones: this.motivaciones,
                marcas: this.marcas
                //completar las variables, estas deben llamarse como las que se recibirán en el backend sin el símbolo del dolar $
            })
            .then((response) => {
            console.log(response.status)
            });
            }

        },
        validar(){
//nombre
          if(this.nombre != "" && !isNaN (this.nombre) === false && this.nombre.length <201 && this.nombre.length > 2 ) {
            console.log("el nombre es correcto")
             
            //edad
            if (this.edad.length < 3 && this.edad != ""){
              console.log("edad existe")
            }else{
              console.log("no existe esa edad")
            }

            //Estado civil
            if (this.estadoCivil != ""){
              console.log("si selecciono estado civil")
            }else{
              console.log("no selecciono estado civil")
              return false
            }

            //Trabajo
            if (this.trabajo.length < 201 && this.trabajo != "" && !isNaN (this.trabajo) === false){
              console.log("trabajo existe")
            }else{
              console.log("no existe trabajo")
              return false
            }

            //Residencia
            if (this.residencia.length < 201 && this.residencia != "" && !isNaN (this.residencia) === false){
              console.log("residencia existe")
            }else{
              console.log("no existe residencia")
              return false
            }

            //Cita
            if (this.cita.length < 501 && this.cita != "" && !isNaN (this.cita) === false){
              console.log("Cita existe")
            }else{
              console.log("Cita no existe")
              return false
            }

            //CitaAutor
            if (this.citaAutor.length < 501 && this.citaAutor != "" && !isNaN (this.citaAutor) === false){
              console.log("CitaAutor existe")
            }else{
              console.log("CitaAutor no existe")
              return false
            }

            //Bio
            if (this.bio.length < 701 && this.bio != "" && !isNaN (this.bio) === false){
              console.log("Bio correcta")
            }else{
              console.log("Bio incorrecta")
              return false
            }

          return true
                       
          }
          else{
            console.log("No pude registrarlo")
            return false
          }
          

            }



    }
}
</script>
<template>
<div class="font-sans">
<form class= "grid grid-cols-3">

  <div class="relative min-h-screen flex flex-col sm:justify-center items-center bg-gray-100 ">
    <div class="relative sm:max-w-sm w-full">
      <div class="card bg-pink-400 shadow-lg  w-full h-full rounded-3xl absolute  transform -rotate-6"></div>
      <div class="card bg-green-400 shadow-lg  w-full h-full rounded-3xl absolute  transform rotate-6"></div>
      <div class="relative w-full rounded-3xl  px-6 py-4 bg-gray-100 shadow-md">
        <label for="" class="block text-sm text-gray-700 text-center font-semibold">
          Formulario de Registro.
        </label>
        <form method="#" action="#" class="mt-10">

          <div>
            <label for="nombre">Ingresa tu nombre</label>
            <input v-model="nombre" type="text" id="nombre"  placeholder="Nombre" class="focus:outline-none pl-2.5 mt-1 block w-full border-none bg-gray-100 h-11 rounded-xl shadow-lg hover:bg-gray-200 focus:bg-gray-100 focus:ring-0">
          </div>

          <div class="mt-7">
            <label for="edad">Ingresa tu edad:</label>
            <input v-model="edad" type="text" id="edad" placeholder="Edad" class="focus:outline-none pl-2.5 mt-1 block w-full border-none bg-gray-100 h-11 rounded-xl shadow-lg hover:bg-gray-200 focus:bg-gray-100 focus:ring-0">
          </div>
          <div>
            <label for="tranbajo">Trabajo</label>
            <input v-model="trabajo" id="trabajo" type="text" placeholder="Trabajo" class="focus:outline-none pl-2.5 mt-1 block w-full border-none bg-gray-100 h-11 rounded-xl shadow-lg hover:bg-gray-200 focus:bg-gray-100 focus:ring-0">
          </div>
          <div>
            <label for="residencia">Residencia</label>
            <input v-model="residencia" id="resindencia" type="text" placeholder="Residencia" class="focus:outline-none pl-2.5 mt-1 block w-full border-none bg-gray-100 h-11 rounded-xl shadow-lg hover:bg-gray-200 focus:bg-gray-100 focus:ring-0">
          </div>
          <div class="mt-7">
            <label class="mt-7">Estado Civil:</label>
                <select v-model="estadoCivil" name="estadoCivil" id="estadoCivil"  class="focus:outline-none pl-2.5 mt-1 block w-full border-none bg-gray-100 h-11 rounded-xl shadow-lg hover:bg-gray-200 focus:bg-gray-100 focus:ring-0" placeholder="Selecciona">
                <option value="1">Soltero</option>
                <option value="2">Casado </option>
                <option value="3">Divorciado</option>
                <option value="4">Separado</option>
                <option value="5">Unión libre</option>
                <option value="6">Viudo</option>
              </select>
                </div>
        </form>
    </div>
    </div>
        </div>
        <div>
          <div class="relative min-h-screen flex flex-col sm:justify-center items-center bg-gray-100 ">
           <div class="relative sm:max-w-sm w-full">
      <div class="card bg-pink-400 shadow-lg  w-full h-full rounded-3xl absolute  transform -rotate-6"></div>
      <div class="card bg-green-400 shadow-lg  w-full h-full rounded-3xl absolute  transform rotate-6"></div>
      <div class="relative w-full rounded-3xl  px-6 py-4 bg-gray-100 shadow-md">
          <label for="cita" class="mt-7">Cita</label>
            <input v-model="cita" id="trabajo" type="text" placeholder="Cita" class="focus:outline-none pl-2.5 mt-1 block w-full border-none bg-gray-100 h-11 rounded-xl shadow-lg hover:bg-gray-200 focus:bg-gray-100 focus:ring-0">
            <div>
            <label for="citaAutor">Cita de CitaAutor</label>
            <input v-model="citaAutor" id="citaAutor" type="text" placeholder="CitaAutor" class="focus:outline-none pl-2.5 mt-1 block w-full border-none bg-gray-100 h-11 rounded-xl shadow-lg hover:bg-gray-200 focus:bg-gray-100 focus:ring-0">
          </div>
          <div>
            <label for="objetivos">Objetivos</label>
            <input v-model="objetivos" id="objetivos" type="text" placeholder="Objetivos" class="focus:outline-none pl-2.5 mt-1 block w-full border-none bg-gray-100 h-11 rounded-xl shadow-lg hover:bg-gray-200 focus:bg-gray-100 focus:ring-0">
          </div>
          <div>
            <label for="frustaciones">Frustraciones</label>
            <input v-model="frustraciones" id="frustaciones" type="text" placeholder="Frustaciones" class="focus:outline-none pl-2.5 mt-1 block w-full border-none bg-gray-100 h-11 rounded-xl shadow-lg hover:bg-gray-200 focus:bg-gray-100 focus:ring-0">
          </div>
          <div>
            <label for="motivaciones">Motivaciones</label>
            <input v-model="motivaciones" id="motivaciones" type="text" placeholder="Motivaciones" class="focus:outline-none pl-2.5 mt-1 block w-full border-none bg-gray-100 h-11 rounded-xl shadow-lg hover:bg-gray-200 focus:bg-gray-100 focus:ring-0">
          </div>
          <div>
            <label for="marcas">marcas</label>
            <input v-model="marcas" id="marcas" type="text" placeholder="Marcas" class="focus:outline-none pl-2.5 mt-1 block w-full border-none bg-gray-100 h-11 rounded-xl shadow-lg hover:bg-gray-200 focus:bg-gray-100 focus:ring-0">
          </div>
      </div>
           </div>
          </div>
          </div>
          <div class="relative min-h-screen flex flex-col sm:justify-center items-center bg-gray-100 ">
           <div class="relative sm:max-w-sm w-full">
      <div class="card bg-pink-400 shadow-lg  w-full h-full rounded-3xl absolute  transform -rotate-6"></div>
      <div class="card bg-green-400 shadow-lg  w-full h-full rounded-3xl absolute  transform rotate-6"></div>
      <div class="relative w-full rounded-3xl  px-6 py-4 bg-gray-100 shadow-md">
          <div class="mt-7">
 <h1 class="mt-7">Personalidad</h1>
  <div>
          <div >
            <label class="block text-black font-bold md:text-left my-2 md:mb-0">
            Personalidad 1.- Mente
          </label><br>
          <div class="flex">
          <h1 class="px-2">Extrovertido  {{ this.Personalidad1 }}% </h1>
          
          <slider @person="pers1">Personalidad 01</slider>
          
          <h1> Introvertido {{100- this.Personalidad1 }}% </h1>
          
        </div>

          </div>

  </div>
        


  <div>
          <div>
            <label>
            Personalidad 2.- Energía
          </label><br>

          <div class="flex">
          <h1 class="px-2">Intuitivo  {{ this.Personalidad2 }}% </h1>
          <slider @person="pers2">Personalidad 02</slider>
            <h1> Observador {{100- this.Personalidad2 }}% </h1>
          
        </div>

          </div>

  </div>

  <div>
          <div>
            <label>
            Personalidad 3.-Naturaleza
          </label><br>

          <div class="flex">
          <h1 class="px-2">Pensamiento  {{ this.Personalidad3 }}% </h1>
          <slider @person="pers3">Personalidad 03</slider> 
         <h1> Emocional {{100- this.Personalidad3 }}% </h1>
          
        </div>


          </div>

  </div>

  <div class="mt-7">
          <div class="mt-7 ">
            <label class="mt-7">
            Personalidad 4.- Identidad
          </label><br>

          <div class="flex">
          <h1 class="px-2">Asertivo {{ this.Personalidad4 }}% </h1>
          <slider @person="pers4">Personalidad 04</slider>
          <h1> Cauteloso {{100- this.Personalidad4 }}% </h1>
          
        </div>

          </div>
          </div>
          </div>
          </div>

  </div>
  </div>
          
          <button @click="Enviar()" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
              ENVIAR
        </button>
          </form>
        </div>
</template>
   