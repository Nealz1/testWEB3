<template>

    <div>
        <button @click="pobierzWpisy">Refresh</button>
        siema blog

        {{ wpisy }}
    </div>

</template>

<script>
import { test_backend } from 'declarations/test_backend/index';

    export default{
        data(){
            return{
                wpisy: []
            }
        },
        methods: {
            async pobierzWpisy(){
            this.wpisy =  await test_backend.odczytaj_wpisy();
            },
        }
    }

</script>