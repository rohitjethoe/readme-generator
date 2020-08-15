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
                <h1>Sub Title</h1>
            </div>
            <input v-model="subtitle" type="text" placeholder="short description about project...">
        </div>
        <div class="section">
            <div class="title">
                <h1>License</h1>
                <select v-model="license" name="license">
                    <option value="MIT">MIT License</option>
                    <option value="APACHE">Apache License 2.0</option>
                    <option value="GNU">GNU General Public License</option>
                    <option value="BSD-2">BSD 2-Clause License</option>
                </select>
            </div>
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
</style>