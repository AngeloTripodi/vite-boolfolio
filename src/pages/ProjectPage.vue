<script>
import axios from 'axios';
import AppSingleProject from '../components/AppSingleProject.vue';

export default {
    name: "ProjectPage",
    components: { AppSingleProject },
    data() {
        return {
            project: null,
            loading: false,
            urlAddress: "http://127.0.0.1:8000/api/projects",
        };
    },
    methods: {
        getProject() {
            axios.get(this.urlAddress + `/${this.$route.params.slug}`, {
                params: {
                }
            })
                .then((response) => {
                    this.project = response.data.results;
                })
                .catch(function (error) {
                    console.warn(error);
                });
        }
    },
    created() {
        this.getProject();
    },

}
</script>

<template>
    <div class="row justify-content-center mt-4">
        <AppSingleProject :project="project" isShow="true" :imgPath="'http://127.0.0.1:8000'" class="col-6" />
    </div>
</template>



<style lang="">
    
</style>