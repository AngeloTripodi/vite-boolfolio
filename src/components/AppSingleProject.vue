<script>
import { stringifyExpression } from '@vue/compiler-core';

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
        },
        'isShow': {
            type: Boolean,
            required: false,
            default: false,
        },
        'imgPath': {
            type: String,
            required: true,
        }

    },
}
</script>

<template>
    <div class="card p-2 mb-3">
        <img v-if="!project.image.startsWith('uploads/')" :src="project.image" alt="{{project.title}}">
        <img v-else :src="imgPath + '/storage/' + project.image" alt="{{project.title}}">

        <div class="card-body">
            <h4>{{ project.title }}</h4>
            <h5>{{ project.author }}</h5>
            <h6>{{ project.project_date }}</h6>
            <p class="card-text">{{ project.content }}</p>
            <h6 class="mt-3 mb-3">{{ project.type.name }}</h6>
            <div v-for="technology in project.technologies">
                <h6>#{{ technology.name }}</h6>
            </div>
            <router-link v-if="!isShow" class="btn btn-primary"
                :to="{ name: 'project', params: { slug: project.slug } }">SHOW
                MORE</router-link>
        </div>

    </div>
</template>

<style lang="">
    
</style>