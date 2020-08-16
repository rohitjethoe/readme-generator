<template>
    <div class="create">
        <div class="section">
            <div class="title">
                <h1>Project Title</h1>
            </div>
            <input v-model="config.title" type="text" placeholder="name...">
        </div>
        <div class="section">
            <div class="title">
                <h1>Subtitle</h1>
            </div>
            <input v-model="config.subtitle" type="text" placeholder="about the project...">
        </div>
        <div class="section">
            <div class="title">
                <h1>Include</h1>
            </div>
            <input v-model="config.installation" class="checkbox" type="checkbox" name="installation" value="installation">
            <label @click="config.installation = !config.installation" for="installation">Getting Started</label>
            <br>
            <input v-model="config.contributing" class="checkbox" type="checkbox" name="contributing" value="contributing">
            <label @click="config.contributing = !config.contributing" for="contributing">Contributing</label>
        </div>
        <div v-if="config.installation" class="section">
            <div class="title">
                <h1>Getting Started</h1>
            </div>
            <input v-model="config.githubName" type="text" placeholder="github username...">
            <br>
            <input v-model="config.repoName" type="text" placeholder="repository name...">
        </div>
        <div class="section">
            <div class="title">
                <h1>License</h1>
            </div>
            <select v-model="config.license" name="license">
                <option value="MIT">MIT License</option>
                <option value="APACHE">Apache License 2.0</option>
                <option value="GNU">GNU General Public License</option>
                <option value="BSD-2">BSD-2 Clause License</option>
            </select>
        </div>
        <div class="button">
            <a @click="$emit('create-readme', config)">Generate README</a>
        </div>
    </div>
</template>

<script>
export default {
    name: "Create",
    data() {
        return {
            config: { 
                title: null, subtitle: null, license: "MIT", installation: false,
                contributing: false, githubName: null, repoName: null
            }
        }
    }
}
</script>

<style scoped>
.create {
	width: 500px;
	margin: 60px auto;
	display: block;
}
.create .section {
	margin-top: 20px;
}
.create .section .title h1 {
	font-size: 21px;
	font-weight: 400;
}
.create .section select {
	margin-top: 20px;
}
.create .section input {
	border: none;
	width: 250px;
	margin-top: 20px;
	border-bottom: #999 1px solid;
	padding-bottom: 10px;
	transition: 0.5s all;
	font-size: 14px;
	color: #999;
}
.create .section input:focus {
	outline: none;
	color: #111;
	border-bottom: #111 1px solid;
}
.create .section .checkbox {
	width: 40px;
}
.create .button {
	margin-top: 30px;
}
.create .button a {
	border: 1px solid #111;
	padding: 6px 60px;
	color: #111;
	transition: 0.2s;
}
.create .button a:hover {
	cursor: pointer;
	-webkit-box-shadow: -2px 3px 2px 3px rgba(0, 0, 0, 0.2);
	-moz-box-shadow: -2px 3px 2px 3px rgba(0, 0, 0, 0.2);
	box-shadow: -2px 3px 2px 2px rgba(0, 0, 0, 0.2);
}
 @media only screen and (max-width: 1000px) {
	.create {
		width: 600px;
	}
	.create .section input {
		width: 300px;
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