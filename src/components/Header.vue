<template>
    <header>

        <b-container class="header" >
            <b-row align-v="center" >
                <b-col cols="4" md="3">
                    <h6>{{ title }}</h6>
                </b-col>

                <b-col cols="4" md="1"></b-col>

                <b-col cols="4" md="4">
                    <img src="../assets/logo.png" alt="">
                </b-col>
                
                <b-col cols="2" md="1"></b-col>
                    
                <b-col cols="10" md="3">
                    <b-list-group horizontal>
                        <b-list-group-item class = "b-list-group-item">
                            <Login/>
                        </b-list-group-item>
                        <b-list-group-item class="b-list-group-item">
                            <Signup/>
                        </b-list-group-item>
                    </b-list-group>
                </b-col>

            </b-row>
        </b-container>


    </header>
</template>


<script>
import Login from './Login.vue'
import Signup from './Signup.vue'

export default {
    name: 'Header',
    props: {
        title: String

    },
    components:{
        Login,
        Signup
    }

}
</script>


<style scoped>
    header{
        /* display: flex; */
        /* justify-content: space-between; */
        /* align-items: center; */
        margin-left: 10px;
        margin-right: 10px;
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

    .b-list-group-item{
        border: none;
    }

</style>