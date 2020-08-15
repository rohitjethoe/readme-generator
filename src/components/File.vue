<template>
    <div class="file">
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
</template>

<script>
export default {
    name: "File",
    props: ["config"]
}
</script>

<style lang="scss">
.file {
    code {
        font-family: "Source Sans Pro", sans-serif;
        .title {
            font-weight: 600;
        }
    }
}
</style>

