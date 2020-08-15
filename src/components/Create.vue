<template>
    <div class="create">
        <div class="section">
            <div class="title">
                <h1>Project Title</h1>
            </div>
            <input v-model="title" type="text" placeholder="name...">
        </div>
        <div class="section">
            <div class="title">
                <h1>Subtitle</h1>
            </div>
            <input v-model="subtitle" type="text" placeholder="about the project...">
        </div>
        <div class="section">
            <div class="title">
                <h1>License</h1>
            </div>
            <select v-model="license" name="license">
                <option value="MIT">MIT License</option>
                <option value="APACHE">Apache License 2.0</option>
                <option value="GNU">GNU General Public License</option>
                <option value="BSD-2">BSD 2-Clause License</option>
            </select>
        </div>
    </div>
</template>

<script>
export default {
    name: "Create",
    data() {
        return {
            title: null, subtitle: null, license: "MIT"
        }
    }
}
</script>

<style lang="scss">
.create {
    width: 500px;
    margin: 60px auto;
    display: block;
    .section {
        margin-top: 20px;
        .title {
            h1 {
                font-size: 21px;
                font-weight: 400;
            }
        }
        select {
            margin-top: 20px;
        }
        input {
            border: none;
            width: 250px;
            margin-top: 20px;
            border-bottom: #999 1px solid;
            padding-bottom: 10px;
            transition: 0.5s all;
            font-size: 14px;
            color: #999;
        }
        input:focus {
            outline: none;
            color: #111;
            border-bottom: #111 1px solid;
        }
    }
}

@media only screen and (max-width: 700px) {
    .create {
        width: 400px;
        margin-top: 60px;
    }
}

@media only screen and (max-width: 464px) {
    .create {
        width: 360px;
        margin-top: 60px;
    }
}
</style>