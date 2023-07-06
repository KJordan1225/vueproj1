<template>
    <teleport to=".modals-container">
        <div class="modal">
            <h1>{{ title }}</h1>
            <slot />
            <button @click="handleButtonClick">Hide Modal</button>
        </div>
    </teleport>
</template>

<script setup>

/*
    Props
*/

const props = defineProps({
    title: {
        type: String,
        default: 'No Title Specified'}
})  

/*
    emits
*/

const emit = defineEmits(['hideModal'])

/*
    handleButtonClick
*/

const handleButtonClick = () => {
    emit('hideModal')
}


</script>

<style>
.modal {
    background: beige;
    padding: 10px;
    position: absolute;
    top: 0;
    left: 0;
    width: 100;
    height:100%;
}
</style>

