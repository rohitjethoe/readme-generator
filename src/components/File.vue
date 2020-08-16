<template>
    <div class="file">
        <div class="code">
            <div class="heading">
                <div class="heading-title">README.md Generated file.</div>
                <div class="heading-return"><a @click="$emit('try-again', true)">Try Again</a></div>
            </div>
            <hr>
            <div class="readme-code">
                <code>
                    <span class="title">
                        # <span v-if="config.emojis">👨🏽‍💻 </span>{{ config.title }}
                    </span>
                    <br>
                    <span class="subtitle"> 
                        {{ config.subtitle }}
                    </span>
                    <br> <br>
                    <div v-if="config.installation" class="getting-started">
                        <span class="title">
                            ## <span v-if="config.emojis">🚀 </span>Getting Started
                        </span>
                        <br>
                        If you have git installed:
                        <br> <br>
                        ```bash
                        <br>
                        git clone https://github.com/{{ config.githubName }}/{{ config.repoName }}.git
                        <br>
                        ```
                    </div>
                    <br>
                    <div v-if="config.contributing" class="contributing">
                        <span class="title">
                            ## <span v-if="config.emojis">📝 </span>Contributing
                        </span>
                        <br>
                        Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.
                        <br> <br>
                        Please make sure to update tests as appropriate.
                    </div>
                    <br>
                    <span class="license">
                        <span class="title">## <span v-if="config.emojis">📜 </span>License</span>
                        <br>
                        <span v-if="config.license === 'MIT'">
                            [MIT License](https://opensource.org/licenses/MIT)
                        </span>
                        <span v-if="config.license === 'APACHE'">
                            [Apache License](https://www.apache.org/licenses/LICENSE-2.0.txt)
                        </span>
                        <span v-if="config.license === 'GNU'">
                            [GNU License](https://www.gnu.org/licenses/gpl-3.0.nl.html)
                        </span>
                        <span v-if="config.license === 'BSD-2'">
                            [BSD-2 Clause License](https://opensource.org/licenses/BSD-2-Clause)
                        </span>
                    </span>
                </code>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "File",
    props: ["config"]
}
</script>

<style scoped>
.file .code .heading {
	font-size: 24px;
	margin-left: 4%;
	padding: 15px 0px;
    margin-top: 10px;
}
.file .code .heading .heading-title {
    float: left;
}
.file .code .heading .heading-return {
    float: right;
    margin-right: 4%;
}
.file .code .heading .heading-return a {
    font-size: 18px;
    padding: 5px 20px;;
	border: 1px solid #111;
    transition: 0.2s all;
}
.file .code .heading .heading-return a:hover {
    cursor: pointer;
	-webkit-box-shadow: -2px 3px 2px 3px rgba(0, 0, 0, 0.2);
	-moz-box-shadow: -2px 3px 2px 3px rgba(0, 0, 0, 0.2);
	box-shadow: -2px 3px 2px 2px rgba(0, 0, 0, 0.2);
}
.file .code .heading::after {
    clear: both;
    content: "";
    display: table;
}
.file .code hr {
	width: 96%;
	border: 0.5px solid;
	margin: 0 auto;
	margin-bottom: 25px;
    margin-top: 10px;
}
.file .code .readme-code {
	width: 80%;
	margin-left: 4%;
}
.file .code code {
	font-family: "Source Sans Pro", sans-serif;
}
.file .code code .title {
	font-weight: 600;
}
</style>
