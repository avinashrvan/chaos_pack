<template>
    <div>


        <b-button id="openButton" class="hidden" v-b-modal.ConfirmModal>Launch demo modal</b-button>

        <b-modal 
            id="ConfirmModal" 
            title="BootstrapVue">
            <p class="my-4">Hello from modal!</p>
        </b-modal>


    </div>
</template>


<script>
export default {
    name: "ConfirmSignUp",
    props:{},
    components:{},
}
</script>



<style scoped>
.hidden{
    display: none;
}

</style>