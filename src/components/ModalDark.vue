<template>
    <teleport to=".modals-container">
        <div
            v-if="modelValue"
            class="modal-dark"
        >
            <h1>{{ title }}</h1>
            <slot />
            <button @click="$emit('update:modelValue',false)">Hide Modal</button>
        </div>
    </teleport>
</template>

<script setup>

/*
    Props
*/

const props = defineProps({
    modelValue: {
		type: Boolean,
		default: false
	},
    title: {
        type: String,
        default: 'No Title Specified'
    }
})  

/*
    emits
*/

const emit = defineEmits(['update:modelValue'])

/*
    handleButtonClick
*/

// const handleButtonClick = () => {
//     emit('update:modelValue',false)
// }


</script>

<style>
.modal {
    background: #333;
    color: white;
    padding: 10px;
    position: absolute;
    top: 0;
    left: 0;
    width: 100;
    height:100%;
}
</style>

