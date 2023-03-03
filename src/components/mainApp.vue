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
        </div>

        <div class="row">
            <div class="col-3 mb-4"  v-for="project in projects">
                <div class="card">
                    
                    <img :src="project.image" alt="{{project.title}}">
                     <div class="card-body">
                     <h4>{{project.title}}</h4>
                     <h5>{{project.author}}</h5>
                     <h6>{{project.project_date}}</h6>
                     <p class="card-text">{{project.content}}</p>
                     <h6 class="mt-3 mb-3">{{project.type.name}}</h6>
                     <div v-for="technology in project.technologies">
                        <h6>#{{technology.name}}</h6>
                     </div>
                    

              </div>
            </div>
            </div>
        </div>
        
        
    </div>
</template>


<style lang="">
    
</style>