<template>
    <header>

        <b-container class="header" >
            <b-row>
                <b-col class='col'>
                    <h6>{{ title }}</h6>
                </b-col>

                <b-col class='col'>
                    <img src="../assets/logo.png" alt="">
                </b-col>
                    
                <b-col class='col'>
                    <h6>LOGIN || SIGNUP</h6>
                </b-col>
            </b-row>
        </b-container>


    </header>
</template>


<script>


export default {
    name: 'Header',
    props: {
        title: String

    },

}
</script>


<style scoped>
    header{
        /* display: flex; */
        justify-content: space-between;
        align-items: center;
        margin-left: 30px;
        margin-right: 30px;
        margin-bottom: 20px;
        margin-top: 20px;
    }

    img{
        /* display: flex; */
        max-width: 60px;
        max-height: 60px;

    }

    .header{
        align-content: center;
    }

</style>