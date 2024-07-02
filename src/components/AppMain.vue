<script>

import axios from "axios";

export default {
    data (){
        return {
            projects: [],
        }
    },

    created(){
        axios.get('http://127.0.0.1:8000/api/projects').then((resp)=>{
            this.projects = resp.data.results;
        });
    }
}
</script>

<template>
<h1 class="text-center mb-5">I miei progetti</h1>
<div class="container">
    <div class="row g-3">
        <div class="col-4" v-for="project in projects">
            <div class="card">
                <div class="card-body">
                    <h5>{{project.title}}</h5>
                    <p>{{ project.content }}</p>
                </div>
            </div>
        </div>
    </div>
</div>
</template>

<style scoped>

</style>