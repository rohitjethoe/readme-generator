<template>
    <div class="header">
        <div class="image">
            <img src="../assets/git-logo.svg" alt="">
        </div>
        <div class="logo">
            README Generator
        </div>
        <div class="subtitle">
            Generate a Project README for your Github repo. 
        </div>
        <div class="repo">
            <div class="icon github">
                <a href="https://github.com/rohitjethoe/readme-generator" target="_blank" rel="noopener" noreferrer>    
                    <i style="font-size: 20px;" class="fab fa-github"></i>
                </a>
            </div>
            <div class="icon stars">
                <a href="https://github.com/rohitjethoe/readme-generator" target="_blank" rel="noopener" noreferrer>
                    <svg aria-hidden="true" role="img" class="star-icon" viewBox="0 0 16 16" width="20" height="20" fill="currentColor"><path fill-rule="evenodd" d="M8 .25a.75.75 0 01.673.418l1.882 3.815 4.21.612a.75.75 0 01.416 1.279l-3.046 2.97.719 4.192a.75.75 0 01-1.088.791L8 12.347l-3.766 1.98a.75.75 0 01-1.088-.79l.72-4.194L.818 6.374a.75.75 0 01.416-1.28l4.21-.611L7.327.668A.75.75 0 018 .25zm0 2.445L6.615 5.5a.75.75 0 01-.564.41l-3.097.45 2.24 2.184a.75.75 0 01.216.664l-.528 3.084 2.769-1.456a.75.75 0 01.698 0l2.77 1.456-.53-3.084a.75.75 0 01.216-.664l2.24-2.183-3.096-.45a.75.75 0 01-.564-.41L8 2.694v.001z"></path></svg>
                </a>
            </div>
            <div class="icon forks">
                <a href="https://github.com/rohitjethoe/readme-generator" target="_blank" rel="noopener" noreferrer>
                    <svg aria-hidden="true" role="img" class="fork-icon" viewBox="0 0 16 16" width="20" height="20" fill="currentColor"><path fill-rule="evenodd" d="M5 3.25a.75.75 0 11-1.5 0 .75.75 0 011.5 0zm0 2.122a2.25 2.25 0 10-1.5 0v.878A2.25 2.25 0 005.75 8.5h1.5v2.128a2.251 2.251 0 101.5 0V8.5h1.5a2.25 2.25 0 002.25-2.25v-.878a2.25 2.25 0 10-1.5 0v.878a.75.75 0 01-.75.75h-4.5A.75.75 0 015 6.25v-.878zm3.75 7.378a.75.75 0 11-1.5 0 .75.75 0 011.5 0zm3-8.75a.75.75 0 100-1.5.75.75 0 000 1.5z"></path></svg>
                </a>
            </div>
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

<style scoped>
.header {
	background-color: #48c9b0;
	padding: 120px 0px;
	color: #fff;
}
.header .image {
	position: absolute;
	top: 0;
	right: 0;
}
.header .logo {
	font-size: 36px;
	display: block;
	text-align: center;
}
.header .subtitle {
	text-align: center;
	font-size: 20px;
}
.header .repo {
	display: flex;
	justify-content: center;
	align-items: center;
	margin-top: 10px;
}
.header .repo .icon {
	margin-left: 10px;
}
 header .repo .icon a:link, .header .repo .icon a:visited {
	color: #fff;
}
.header .repo .github {
	transform: translateY(-2px);
}
 @media only screen and (min-width: 800px) {
	.header .logo {
		font-size: 36px;
	}
	.header .subtitle {
		font-size: 20px;
	}
}
</style>