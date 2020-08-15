<template>
    <div class="file">
        <div class="code">
            <div class="heading">
                README.md Generated file.
            </div>
            <hr>
            <div class="readme-code">
                <code>
                    <span class="title">
                        # {{ config.title }}
                    </span>
                    <br>
                    <span class="subtitle"> 
                        {{ config.subtitle }}
                    </span>
                    <br> <br>
                    <div v-if="config.installation" class="getting-started">
                        <span class="title">
                            ## Getting Started
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
                            ## Contributing
                        </span>
                        <br>
                        Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.
                        <br> <br>
                        Please make sure to update tests as appropriate.
                    </div>
                    <br>
                    <span class="license">
                        <span class="title">## License</span>
                        <br>
                        <span v-if="config.license === 'MIT'">
                            [MIT License](https://opensource.org/licenses/MIT)
                        </span>
                        <span v-if="config.license === 'APACHE'">
                            [Apache License](https://www.apache.org/licenses/LICENSE-2.0.txt)
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

<style lang="scss">
.file {
    .code {
        .heading {
            font-size: 24px;
            margin-left: 4%;
            padding: 15px 0px;
        }
        hr {
            width: 96%;
            border: 0.5px solid;
            margin: 0 auto;
            margin-bottom: 10px;
        }
        .readme-code {
            width: 80%;
            margin-left: 4%;
        }
        code {
            font-family: "Source Sans Pro", sans-serif;
            .title {
                font-weight: 600;
            }
        }
    }
}
</style>

