<template>
    <div class="header">
        <div class="logo">
            README Generator
        </div>
        <div class="subtitle">
            Generate a Project README for your Github repo. 
        </div>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    name: "Header", 
    data() {
        return {
            data: null
        }
    },
    mounted() {
        this.getRepoData();
    },
    methods: {
        getRepoData() { 
            axios.get('https://api.github.com/repos/rohitjethoe/readme-generator')
            .then((res) => {
                this.data = res.data 
            })
        }
    }
}
</script>

<style lang="scss">
    .header {
        .logo {
            font-size: 28px;
            display: block;
            text-align: center;
            color:#85c1e9; 
        }
        .subtitle {
            text-align: center;
            font-size: 18px;
            color: #474747;
        }
    }
</style>