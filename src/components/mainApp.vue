<script>
import axios from 'axios';

export default {
    name: 'mainApp',
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
    created() {
        this.getProjects();
    }

}
</script>

<template lang="">
    <div class="container">
        <div class="row">
            <div class="col-12">
                <h1>
                    Projects:
                </h1>
            </div>
            <div class="card text-start" v-for="project in projects">
              <!-- <img class="card-img-top" src="holder.js/100px180/" alt="Title">
              <div class="card-body"> -->
                <h4 class="card-title">{{project.title}}</h4>
                <!-- <p class="card-text">Body</p> -->
              <!-- </div> -->
            </div>
        </div>

        
        
    </div>
</template>


<style lang="">
    
</style>