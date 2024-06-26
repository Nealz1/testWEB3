<template>
    <div>
        <button @click="pobierzWpisy">refresh</button>
        siema blog!
        {{ wpisy }}
        <input v-model="nowyBlog" type="text">
        <button @click="dodajWpisy">dodaj</button>
    </div>
</template>

<script>
import { test_backend } from 'declarations/test_backend/index';

export default {
    data() {
        return {
            wpisy: [],
            nowyBlog: ""
        }
    },
    methods: {
        async dodajWpisy() {
            await test_backend.dodaj_wpis(this.nowyBlog);
        },
        async pobierzWpisy() {
            this.wpisy = await test_backend.odczytaj_wpisy();
        }
    },
}
</script>