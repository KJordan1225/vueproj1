<template>
    <div class="modals">
        <h1>Modals</h1>
        <button @click="showModal = true">Show Modal</button>   
        <Modal
          v-model="showModal"                   
        >            
            <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Neque temporibus consequuntur, 
                illum iste molestias cupiditate perspiciatis! Pariatur tempore, beatae, tenetur ipsam 
                cupiditate dolor laboriosam autem ullam minus ad obcaecati provident!</p>
        </Modal>  
    </div>
</template>

<script setup>
    /*
        Imports
    */
    
    import { ref } from 'vue'   
    import Modal from '@/components/Modal.vue'     


    /*
        Modals
    */
    
    const showModal = ref(false)

</script>

