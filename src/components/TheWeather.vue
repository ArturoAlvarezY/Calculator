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
const icon = ref(defaultIcon);
const stateSky = ref('');



const fetchWeather = async () => {
    try{
        let uri = 'https://www.el-tiempo.net/api/json/v2/provincias/33/municipios/33024';
        const response = await fetch(uri);
        let data = await response.json();
        // let sky = stateSky.value
        city.value = data.municipio.NOMBRE;
        temperature.value = data.temperatura_actual;
        stateSky.value = data.stateSky.description.toLowerCase();
        console.log(data);

        if(stateSky.value.includes('tormenta')){
            icon.value= stormIcon;
        }
        else if(stateSky.value.includes('lluvia')){
            icon.value= rainIcon;
        } 
        else if (stateSky.value.includes('nuboso') || stateSky.value.includes('cubierto')) {
            icon.value = cloudyIcon;
        }
        else if (stateSky.value.includes('despejado')){
            icon.value= clearIcon;
        }
        else if(stateSky.value.includes('humedo')){
            icon.value= wetIcon;
        }
        else if(stateSky.value.includes('nubes altas')){
            icon.value= hightCloudIcon;
        } else {
            icon.value = defaultIcon;
        }
        
    }
    catch(error) {
        console.error('Error loading data', error); 
    }
}

onMounted(fetchWeather);

</script>

<template>
    <div class="weather">
        <h2>{{ city }}</h2>
        <img :src="icon" alt="weather icon" />
        <div>
            <h3>{{ temperature }}°C</h3>
            <p>{{ stateSky }}</p>            
        </div>
    </div>
</template>


<style lang="scss" scoped>

.weather {
    background-color: #2C3051;
    padding: 20px;
    max-width: 310px;
    border-radius: 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;

        div {
            text-align: right;
        }
}
</style>