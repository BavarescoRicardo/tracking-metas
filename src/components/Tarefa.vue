<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div class="box has-text-weight-bold">
        <div class="column is-7">
            {{ tarefa.descricao }}
        </div>
        <div class="column is-3">
            {{ tarefa.contagem }}
        </div>        
    </div>
</template>
<script lang="ts">

import ITarefa from '@/interfaces/ITarefa';
import { defineComponent, PropType } from 'vue';

export default defineComponent ({
    // eslint-disable-next-line vue/multi-word-component-names
    name: 'Tarefa',
    props: {
        tarefa: {
            type: Object as PropType<ITarefa>,
            required: true
        }
    },
  
})    
</script>
<style scoped>
.box {
    background-color: #dbeaff;
}
    
</style>