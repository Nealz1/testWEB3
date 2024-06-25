<template>
    <div>
        Siema blog!
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
    }
    methods: {
        .async pobierzWpisy(){
            test_backend
        }
    },
}
</script>