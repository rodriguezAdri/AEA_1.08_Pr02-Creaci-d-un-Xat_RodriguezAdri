<template>
    <div>
        <h1>Xat entre Usuaris</h1>
        <Missatge :autor="autor" @enviarMissatge="afegirMissatge"/>
        <ul>
            <li v-for="(msg, index) in missatges" :key="index">
                <strong>{{ msg.autor }}: </strong> {{ msg.text }}
            </li>
        </ul>
    </div>
</template>

<script setup>
import { ref } from 'vue';
import Missatge from './Missatge.vue';

const autor = 'Usuari 1';
const missatges = ref([]);

const afegirMissatge = (nouMissatge) => {
    missatges.value.push(nouMissatge);
};
</script>