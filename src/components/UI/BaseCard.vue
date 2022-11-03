<template>
    <div id="card">
        <slot></slot>
    </div>
</template>

<style>
    div#card{
        box-shadow: 1px 1px 6px 1px lightgrey;
        padding: 8px 32px;
        border-radius: 15px;
        width: 80%;
        margin: 2rem auto;
    }
</style>