<script lang="ts">
import { defineComponent } from 'vue'
import Navegacao from './Navegacao.vue'


export default defineComponent({
    data() {
        return {
            resultado: [],
            inputFocus: false
        };
    },
    methods: {
        setFocus(v: boolean) {
            this.inputFocus = v;
        }
    },
    components: { Navegacao }
});
</script>

<template>
    <header class="container-header">
        <div class="principal">
            <img src="../assets/imagens/logo-horizontal.svg" alt="logo devagram" />
            <div class="group">
                <div class="pesquisa" :class="{ focus: inputFocus }">
                    <img src="../assets/imagens/busca.svg" alt="pesquisa" layout="fill" class="icon" />
                    <input type="text" placeholder="Pesquisar" @focus="setFocus(true)" @blur="setFocus(false)" />
                </div>

                <!-- Navegacao-->
                <Navegacao />
            </div>
        </div>
         <!-- Resultado da busca -->
        <div class="resultado" v-if="resultado.length > 0"> 
        </div>
    </header>
</template>


<style lang="scss" src="@/assets/styles/header.scss" />
