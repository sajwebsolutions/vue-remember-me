<template>
    <ul>
        <learning-resource v-for="res in resources"
                           :key="res.id"
                           :id="res.id"
                           :title="res.title"
                           :description="res.description"
                           :link="res.link"
        ></learning-resource>
    </ul>
</template>

<script>

    //Import
    import LearningResource from "./LearningResource";

    export default {
        //Register
        components:{
            LearningResource
        },

        //Inject
        inject: ['resources'],


    }
</script>
