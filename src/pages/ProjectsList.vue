<script>
import AppSingleProject from '../components/AppSingleProject.vue';
import axios from 'axios';


export default {
    name: "ProjectsList",
    data() {
        return {
            projects: [],
            loading: false,
            urlAddress: 'http://127.0.0.1:8000/api/projects',
        }
    },
    methods: {
        getProjects() {
            axios.get(this.urlAddress, {
                params: {

                }

            })
                .then((response) => {
                    this.projects = response.data.results.data;
                })
                .catch(function (error) {
                    console.warn(error);
                })
        }
    },
    components: { AppSingleProject },
    created() {
        this.getProjects();
    }

}
</script>

<template>
    <div class="container">
        <div class="row">
            <div class="col-12">
                <h1>
                    Projects:
                </h1>
            </div>
        </div>

        <div class="row card-container">

            <AppSingleProject v-for="project in projects" :project="project" :imgPath="'http://127.0.0.1:8000'"
                class="col-3" />

        </div>
    </div>
</template>



<style lang="">
    
</style>