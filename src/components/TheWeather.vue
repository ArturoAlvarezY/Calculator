<template>
    <div class="weather">
        weather here
        <h2>{{ city }}</h2>
        <p>{{ temperature }}</p>
        <img :src="icon" alt="weather icon" />
        <p>{{ stateSky }}</p>
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import cloudyIcon from '@/assets/nuboso.png';
import clearIcon from '@/assets/despejado.png'
import wetIcon from '@/assets/humedo.png'
import rainIcon from '@/assets/Lluvia.png'
import stormIcon from '@/assets/tormenta.png'
import hightCloudIcon from '@/assets/nubes-altas.png'
import defaultIcon from '@/assets/default.png'

const city = ref('');
const temperature = ref('');
const icon = ref('');
const stateSky = ref('');


const fetchWeather = async () => {
    try{
        let uri = 'https://www.el-tiempo.net/api/json/v2/provincias/33/municipios/33024';
        const response = await fetch(uri);
        let data = await response.json();
        let sky = stateSky.value
        city.value = data.municipio.NOMBRE;
        temperature.value = data.temperatura_actual;
        sky = data.stateSky.description.toLowerCase();
        console.log(data);

        if (sky.includes('nuboso') || sky.includes('cubierto')) {
            icon.value = cloudyIcon;
        }

        else if (sky.includes('despejado')){
            icon.value= clearIcon;
        }

        else if(sky.includes('humedo')){
            icon.value= wetIcon;
        }
        else if(sky.includes('lluvia')){
            icon.value= rainIcon;
        } 

        else if(sky.includes('tormenta')){
            icon.value= stormIcon;
        }
        else if(sky.includes('nubes altas')){
            icon.value= hightCloudIcon;
        }else{
            icon.value= defaultIcon;
        }
        
        
    }
    catch(error) {
        console.error('Error loading data', error); 
    }
}

onMounted(fetchWeather);

</script>

<style lang="scss" scoped>
.weather {
    background-color: #2C3051;
    padding: 20px;
}
</style>