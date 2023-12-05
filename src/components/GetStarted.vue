<template>
    <div>

        <b-container class="b-container">
            <b-row>
                <b-col class='col'>
                    <h3>Personal Budget Tracking Tool</h3>
                    <h5>One Stop Budget Tracking Solution</h5>
                    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam id est laborum.</p>
                    <InputEmail/>

                </b-col>


                <b-col class='col'>2 of 2</b-col>
            </b-row>
        </b-container>



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