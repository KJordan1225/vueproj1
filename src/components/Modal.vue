<template>
    <teleport to=".modals-container">
        <div
            v-if="modelValue"
            class="modal"
        >
            <h1><slot name="title"></slot></h1>
            <slot />
            <button @click="$emit('update:modelValue',false)">Hide Modal</button>     
            <div>
                Username is: {{ userData.username }}
            </div>       
        </div>
    </teleport>
</template>

<script setup>
  /*
    imports
  */

  import { inject } from 'vue'

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
    userData
*/

const userData = inject('userData')

/*
    handleButtonClick
*/

// const handleButtonClick = () => {
//     emit('update:modelValue',false)
// }


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

