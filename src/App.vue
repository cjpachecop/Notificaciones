<script setup>
import {ref} from 'vue';
let notificacion = ref()
function addvalue() {
  notificacion.value++
  console.log(notificacion);

}
function minusValue() {
  if(notificacion.value >= 1){
  notificacion.value--
  console.log(notificacion);
}
  
}

</script>

<template>
  <div class="wrapper">
  <div class="profile">
    
    <div class="notificacion" v-if="notificacion > 0">{{notificacion}}</div>
  </div>
  <div class="button-wrapper">
    <div class="button" @click="minusValue">-</div>
    <div class="button" @click="addvalue" >+</div>
   </div>
   <div v-if="notificacion == 0">Buu! Nadie te escribe 🤣</div>
   <div v-else>Revisa tu inbox😎</div>
  </div>
</template>

<style scoped>
.wrapper{
background-color: green;
width: 60%;
border-radius: 8px;
margin: 0 auto;
padding-top: 32px;
overflow: hidden;

}

.profile{
background-color: purple;
width: 120px;
height: 120px;
border-radius: 100%;
margin: 0 auto;
margin-top: 0;
position: relative;
background-image: url('https://media.licdn.com/dms/image/D4E03AQE0rZD6Es-Gng/profile-displayphoto-shrink_400_400/0/1691898116177?e=1701907200&v=beta&t=sbrwxMF1uzf694ivF2tdvDOV3jNMCIV3Y9dud2AZiJE');
background-size: cover;
}

.notificacion{
background-color: red;
min-width: 18px;
height: 18px;
border-radius: 100%;
position: absolute;
color: white;
justify-content: center;
top: 0;
right: 0;
padding: 2px;
}

.button-wrapper{

text-align: center;
margin-top: 12px;
padding-bottom: 16px;


}

.button{
background-color: peru;
border-radius: 4px;
padding: 2px 0;
font-weight: bold;
color: white;
display: inline-block;
width: 40px;
margin-left: 12px;
cursor: pointer;
}

.button:first-child{
margin-right:8px;



}

.button:last-child{
margin-left:8px;



}



</style>
