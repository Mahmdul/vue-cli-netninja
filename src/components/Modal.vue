<template>
    <div class="backdrop" @click="closeModal">
        <div class="modal" :class="{ bla: theme ==='sale' }"> <!--Here ":class" means dynamic class binding or data binding. Here the first "sale" is name of class, we can also say "key"-->
            <h1>{{ header }}</h1>
            <p>{{ text }}</p>
        </div>

    </div>
</template>

<script>
    export default {
        props: ['header', 'text', 'theme'], // here we pass data "header" from parent component to child component using props
        methods: {
            closeModal(){
                this.$emit('close') // here "close" is custom event which is triggered in App.vue component(parent)
            }
        } 
    }
</script>

<style scoped>
    .modal {
        width: 400px;
        padding: 20px;
        margin: 100px auto;
        background: white;
        border-radius: 10px;
    }
    .backdrop {
        top: 0;
        position: fixed;
        background: rgba(0, 0, 0, 0.5);
        width: 100%;
        height: 100%;
    }
    h1 {
        color: #03cfb4;
        border: none;
        padding: 0;
    }
    .modal.bla {
        background: crimson;
        color: white;

    }
    .modal.bla h1 {
        color: white;
    }
</style>