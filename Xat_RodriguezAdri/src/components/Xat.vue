<template>
    <div>
        <h1>Xat entre Usuaris</h1>
        <Missatge :autor="autor" @enviarMissatge="afegirMissatge"/>
        <ul>
            <li v-for="(missatge, index) in missatges" :key="index">
                <strong>{{ missatge.autor }};</strong> {{ missatge.text }}
            </li>
        </ul>
    </div>
</template>

<script setup>
import { ref } from 'vue';
import Missatge from './Missatge.vue';

const autor = 'Usuari 1';
const missatges = ref([]);

const afegirMissatge = (missatge) => {
    missatges.value.push(missatge);
};
</script>