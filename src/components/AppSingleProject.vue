<script>
export default {
    name: 'AppSingleProject',
    data() {
        return {

        }
    },
    props: {
        'project': {
            type: Object,
            required: true,
        }
    },
}
</script>

<template lang="">
                <div class="card w-100">
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
</template>

<style lang="">
    
</style>