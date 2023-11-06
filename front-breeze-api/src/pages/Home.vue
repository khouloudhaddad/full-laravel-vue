<script setup>
import { ref, onMounted } from "vue";
import axios from "axios"

const user = ref();

onMounted(async () => {
    const data = await axios.get('/api/user');
    user.value = data.data
})
</script>

<template>
    <div>
        Home page {{ user.message }}
    </div>
</template>

<style lang="sass" scoped>

</style>