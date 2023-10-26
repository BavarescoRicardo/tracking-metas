<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div class="box">
        <div class="columns">
            <div class="column is-8" role="form" aria-label="Formulário para criação de objetivo">
                <input type="text" class="input" placeholder="Qual meta você quer monitorar?" v-model="meta">
            </div>
            <div class="column">
                <div class="is-flex is-align-itens-center is-justify-content-space-between">
                    <Objetivos :contagem="contagem"/>

                    <button class="button" @click="iniciar" :disabled="cronometroRodando">
                        <span class="icon">
                            <i class="fas fa-play"></i>
                        </span>
                        <span>play</span>
                        </button>
                        <button class="button" @click="finalizar" :disabled="!cronometroRodando">
                        <span class="icon">
                            <i class="fas fa-stop"></i>
                        </span>
                        <span>stop</span>
                    </button>          
                </div>    
            </div>
        </div>
    </div>
</template>
<script lang="ts">

import { defineComponent } from 'vue';
import Objetivos from '../components/Objetivos.vue'

export default defineComponent ({
    // eslint-disable-next-line vue/multi-word-component-names
    name: 'Formulário',
    emits: ['aoSalvar'],
    components: {
        Objetivos
    },
    data () {
        return {
            contagem: 0,
            crono: 0,
            cronometroRodando: false,
            meta: ''
        }
    },
    methods: {
        iniciar () {
            this.cronometroRodando = true
            console.log('inicio');
            this.crono = setInterval( () => {
                this.contagem += 1;
            }, 1000)
        },
        finalizar () {
            this.cronometroRodando = false
            console.log('fim');
            clearInterval(this.crono);
            this.gravarObjetivo(this.contagem)
        },
        gravarObjetivo (contagem: number) {
            this.$emit('aoSalvar', {
                descricao: this.meta,
                contagem: contagem
            })
            console.log("fim da tarefa")
            console.log("Vezes executada: "+ contagem)
            console.log("Nome da tarefa:  " + this.meta)
        }        
    }
    
})
</script>
<style lang="">
    
</style>