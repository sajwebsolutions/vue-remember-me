<template>
    <li>
        <base-card>
            <header>
                <h3>{{ title }}</h3>
                <base-button mode="flat" @click="deleteResource('id')">Delete</base-button>
            </header>

            <p>{{ description }}</p>
            <nav>
                <a :href="link">View Resource</a>
            </nav>
        </base-card>
    </li>
</template>

<script>
    export default {
        inject: ['deleteResource'],
        props: ['id', 'title', 'description', 'link']
    }
</script>


<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300&display=swap');

    li{
        list-style-type: none;
        margin-top: 10px;
        width: 80%;
    }

    header{
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    header h3{
        font-size: 28px;
    }

    nav a{
        color: darkgoldenrod;
        font-size: 14px;
    }

    p{
        font-family: Poppins;
    }
</style>