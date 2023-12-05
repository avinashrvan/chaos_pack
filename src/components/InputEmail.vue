<template>
    <div>
        <b-input-group class="mt-3">

            <b-form-input class="in"></b-form-input>

            <b-input-group-append>
                <b-button class="submit" pill variant="light">Get Started</b-button>
            </b-input-group-append>
        </b-input-group>
    </div>
</template>


<script>
export default {
    name: "InputEmail",
    props: {
        placeholder: String,
        submitWord: String,
    },

    data(){
        return{
            text: ''
        }
    }
}
</script>

<style scoped>
    .in{
        border-radius: 20px;
        border-color: black;
    }

    .submit{
        background-color: darkorange;
        -webkit-text-fill-color: white;
        width: 150px;
    }
</style>