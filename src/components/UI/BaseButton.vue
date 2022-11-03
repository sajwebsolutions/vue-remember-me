<template>
    <button :type="type" :class="mode">
        <slot></slot>
    </button>
</template>

<script>
    export default {
        props: ['type', 'mode']
    }
</script>

<style>
    button{
        box-shadow: 1px 1px 6px 1px lightgrey;
        padding: 15px;
        background-color: red;
        border: none;
        color: white;
        cursor: pointer;
    }

    .flat:hover{
        background-color: darkred;
    }

    .inactive{
        background-color: lightgrey;
        padding: 15px;
        color: white;
        cursor: pointer;
        border: none;
    }


    .active{
        background-color: lightseagreen;
        padding: 15px;
        color: white;
        cursor: pointer;
        border: none;
    }
</style>

