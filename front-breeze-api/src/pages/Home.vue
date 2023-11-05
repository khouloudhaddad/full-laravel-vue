<script>
import { ref, onMounted } from "vue";
import axios from "axios"

const user = ref();

onMounted(async()=>{
    const data = await axios.get('/api/user/');
    console.log(data.data);
})
</script>

<template>
    <div>
        Home page
    </div>
</template>

<style lang="sass" scoped>

</style>