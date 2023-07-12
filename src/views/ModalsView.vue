<template>
    <div class="modals">
        <h1>Modals</h1>
        <button @click="showModal = true">Show Modal !!!</button> 
        <div>
            Show dark modals?
            <input 
                v-model="showDarkModals"
                type="checkbox"
            />
        </div>  
        <Modal v-if="showModal">
            <template #title>Myn New Title</template>
            <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Neque temporibus consequuntur, 
                illum iste molestias cupiditate perspiciatis! Pariatur tempore, beatae, tenetur ipsam 
                cupiditate dolor laboriosam autem ullam minus ad obcaecati provident!</p>
        </Modal>
        <component
          v-model="showModal" 
          :is="showDarkModals ? ModalDark : Modal" 
        >            
            <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Neque temporibus consequuntur, 
                illum iste molestias cupiditate perspiciatis! Pariatur tempore, beatae, tenetur ipsam 
                cupiditate dolor laboriosam autem ullam minus ad obcaecati provident!</p>
        </component>  
    </div>
    <div>
        <button
            class='counter-button' 
            @click="increaseCounter(1)"
            :class="{yellow : oddOrEven === 'odd'}">
            {{ counterData.count }}
        </button>
    </div>
</template>

<script setup>
    /*
        Imports
    */
    
    import { ref } from 'vue'   
    import Modal from '@/components/Modal.vue'
    import ModalDark from '@/components/ModalDark.vue' 
    import {useCounter} from '@/use/useCounter'
    
    
    /*
        Modals
    */
    
    const showDarkModals = ref(false)
    const showModal = ref(false)

    /*
        counter button
    */

    const {counterData, increaseCounter, oddOrEven} = useCounter()

    

</script>

<style scoped>
.counter-button {
    font-size: 60px;
    background-color: pink;
    width: 100%;
}

.counter-button.yellow {
    background-color: yellow
}
</style>

