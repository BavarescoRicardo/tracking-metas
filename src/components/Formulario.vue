<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div class="box">
        <div class="columns">
            <div class="column is-8" role="form" aria-label="Formulário para criação de objetivo">
                <input type="text" class="input" placeholder="Qual meta você quer monitorar?">
            </div>
            <div class="column">
                <div class="is-flex is-align-itens-center is-justify-content-space-between">
                    <section>
                        <strong>{{ tempoDecorrido }}</strong>
                    </section>
                    <button class="button" @click="iniciar">
                        <i class="fas fa-play"></i>
                        <span>play</span>
                    </button>
                    <button class="button" @click="finalizar">
                        <i class="fas fa-stop"></i>
                        <span>stop</span>
                    </button>            
                </div>    
            </div>
        </div>
    </div>
</template>
<script lang="ts">

import { defineComponent } from 'vue';

export default defineComponent ({
    // eslint-disable-next-line vue/multi-word-component-names
    name: 'Formulário',
    data () {
        return {
            tempo: 0,
            crono: 0
        }
    },
    computed: {
        tempoDecorrido () {
            return new Date(this.tempo * 1000).toISOString().substring(11,19);
        }
    },
    methods: {
        iniciar () {
            console.log('inicio');
            this.crono = setInterval( () => {
                this.tempo += 1;
            }, 1000)
        },
        finalizar () {
            console.log('fim');
            clearInterval(this.crono);
        },        
    }
    
})
</script>
<style lang="">
    
</style>