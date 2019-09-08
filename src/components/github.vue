<template>
    <div class="container-fluid">
        <button @click="githubUsers">Get Users</button>
        <div class="row">
            <div class="d-flex flex-wrap justify-content-center">
                <div v-for="user in users" v-bind:key="user.id">
                    <div class="card m-3" style="width: 18rem;">
                        <img :src="user.avatar_url" class="card-img-top" alt="avatar">
                        <div class="card-title">
                            {{user.login}}
                        </div>
                        <div class="card-text">
                            {{user.bio}}
                        </div>
                        <a class="card-link btn btn-info" :href="user.html_url">Github Page</a>
                    </div>
                </div>

            </div>
        </div>
    </div>

</template>

<script>
    import axios from 'axios';

    export default {
        name: "github",
        data(){
            return{
                userName:'',
                users:[],
                user:[]
            }

        },
        methods: {
            async githubUsers(){
                const users = await axios({
                    method:'get',
                    url: 'https://api.github.com/users',
                    Authorization: `token ${process.env.GITHUB_TOKEN}`
                });
                const {data} = users;
                this.users = data;
            },

        }

    }
</script>

<style scoped>

</style>