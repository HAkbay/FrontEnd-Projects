<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal">
            <slot>Default</slot>
            <div class="actions">
                <slot name="buttons"></slot>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: [],
        methods: {
            closeModal() {
                this.$emit('close');
            }
        }
    }
</script>

<style>
    .modal{
        width: 400px;
        padding: 20px;
        margin: 100px auto;
        background: black;
        color: white;
        border-radius: 10px;
    }
    .modal .actions{
        text-align: center;
        margin: 30px 0 10px 0;
    }
    .modal .actions a{
        color: crimson;
        padding: 8px;
        border: 1px solid white;
        border-radius: 4px;
        text-decoration: none;
        margin: 10px;
    }
    .backdrop{
        top: 0;
        position: fixed;
        background: rgba(0,0,0,0.5);
        width: 100%;
        height: 100%;
    }
</style>