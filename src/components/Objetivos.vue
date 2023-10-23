<template lang="">
    <div>
        <section>
            <strong>{{ tempoDecorrido }}</strong>
        </section>        
    </div>
</template>
<script lang="ts">

import { defineComponent } from 'vue';

export default defineComponent ({
    // eslint-disable-next-line vue/multi-word-component-names
    name: 'Objetivos',
    props: {
        contagem: {
            type: Number,
            default: 0
        }
    },
    computed: {
        tempoDecorrido () {
            return new Date(this.contagem * 1000).toISOString().substring(11,19);
        }
    }    
})    
</script>
<style lang="">
    
</style>