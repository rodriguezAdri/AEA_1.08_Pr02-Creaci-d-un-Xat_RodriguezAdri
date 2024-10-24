<template>
    <div>
        <input v-model="missatge" placeholder="Escriu el teu missatge..."/>
        <button @click="enviarMissatge">Enviar</button>
    </div>    
</template>

<script setup>
import { ref } from 'vue';
import { defineProps, defineEmits } from 'vue';

const props = defineProps({
    autor: {
        type: String,
        required: true
    }
});

const emit = defineEmits(['enviarMissatge']);
const missatges = ref('');


const enviarMissatge = () => {
    if (missatges.value.trim()){
        const nouMissatge = {
            autor: props.autor,
            text: missatges.value
        };
        emit('enviarMissatge', nouMissatge);
        missatges.value = '';
    }
}
</script>