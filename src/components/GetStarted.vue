<template>
    <div>

        <b-container class="b-container">
            <b-row align-v="center">
                <b-col class='col'>
                    <h3 style="color:#00008B; font-family: Helvetica"><strong>Personal Budget Tracking Tool</strong></h3>
                    <h6><em>One Stop Budget Tracking Solution</em></h6>
                    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam id est laborum.</p>
                    <InputEmail/>

                </b-col>

                <b-col class='col'>
                    <img src="../assets/getStarted.png" class="img-responsive float-end" width="100%">                
                </b-col>
            </b-row>
        </b-container>
        <h3 class="hidden">space</h3> 
    </div>
</template>


<script>
import InputEmail from './InputEmail.vue'

export default {
    name: 'GetStarted',
    props: {
        

    },
    components: {
        InputEmail,
    }

}
</script>


<style scoped>
    .b-container{
        text-align: left;
    }
</style>