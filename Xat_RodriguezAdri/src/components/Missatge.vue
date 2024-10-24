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
const missatge = ref('');


const enviarMissatge = () => {
    if (missatge.value.trim()){
        const nouMissatge = {
            autor: props.autor,
            text: missatge.value
        };
        emit('enviarMissatge', nouMissatge);
        missatge.value = '';
    }
}
</script>