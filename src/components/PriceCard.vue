<template>
    <div id="main">

        <!-- CODE FOR FREE AND PRO CARDS -->
        <div class="poster shadow" v-if="title !== 'Premium'">

            <h5 style="color:#00008B; font-family: Helvetica"><strong>{{ title }}</strong></h5>
            <h6>For {{ forWho }}</h6>

            <div class="hidden">space</div>

            <h1 style="color:#00008B; font-family: Helvetica"><strong>{{ price }}</strong></h1>

            <div class="hidden">space</div>


            <ul class="list-group list-group-flush">
                <li class="list-group-item d-flex ">
                    <b-badge pill variant="danger" class="badge">ii</b-badge>
                    <div class="hidden">ss</div>
                    <strong>{{ sp1 }}</strong></li>
                <li class="list-group-item d-flex ">
                    <b-badge pill variant="danger" class="badge">ii</b-badge>
                    <div class="hidden">ss</div>
                    <strong>{{ sp2 }}</strong></li>
                <li class="list-group-item d-flex ">
                    <b-badge pill variant="danger" class="badge">ii</b-badge>
                    <div class="hidden">ss</div>
                    <strong>{{ sp3 }}</strong></li>
            </ul>

            <div class="hidden">y</div>
            <div class="hidden">y</div>

            <ModalFormFree v-if="title === 'Free'" initial="Free"></ModalFormFree>
            <ModalFormPro v-if="title === 'Pro'" initial="Pro"></ModalFormPro>

        </div>
        

        <!-- CODE FOR THE BLUE POSTER ONLY FOR PREMIUM CARD -->
        <div class="poster blue shadow" v-if="title === 'Premium'">

            <h5 style="color:rgb(231, 231, 231); font-family: Helvetica"><strong>{{ title }}</strong></h5>
            <h6 style="color:rgb(231, 231, 231);">For {{ forWho }}</h6>

            <div class="hidden">space</div>

            <h1 style="color:rgb(231, 231, 231); font-family: Helvetica"><strong>{{ price }}</strong></h1>

            <div class="hidden">space</div>


            <ul class="list-group list-group-flush">
                <li class="list-group-item d-flex blue">
                    <b-badge pill variant="danger" class="blueBadge">ii</b-badge>
                    <div class="hidden">ss</div>
                    <strong>{{ sp1 }}</strong></li>
                <li class="list-group-item d-flex blue">
                    <b-badge pill variant="danger" class="blueBadge">ii</b-badge>
                    <div class="hidden">ss</div>
                    <strong>{{ sp2 }}</strong></li>
                <li class="list-group-item d-flex blue">
                    <b-badge pill variant="danger" class="blueBadge">ii</b-badge>
                    <div class="hidden">ss</div>
                    <strong>{{ sp3 }}</strong></li>
            </ul>

            <div class="hidden">y</div>
            <div class="hidden">y</div>
            <div class="hidden">y</div>

            <ModalForm initial="Premium"/>

        </div>



        
        <div class="hidden">y</div>
        <div class="hidden">y</div>

    </div>
</template>



<script>
import ModalForm from './ModalForm.vue'
import ModalFormFree from './ModalFormFree.vue' 
import ModalFormPro from './ModalFormPro.vue'

export default {
    name: "PriceCard",
    components:{
        ModalForm,
        ModalFormFree,
        ModalFormPro
    },
    props:{
        title: String,
        forWho: String,
        price: String,
        pointColor: String,
        sp1: String,
        sp2: String,
        sp3: String

    }
}
</script>



<style scoped>
.list-group-item {
    border-color: white;
}

.badge{
    background-color: darkblue;
    -webkit-text-fill-color: darkblue;
    border-radius: 13px;
    max-height: 22px;
}

.poster{
    background-color: white;
    align-content: left;
    text-align: left;
    padding-top: 40px;
    padding-bottom: 40px;
    padding-left: 50px;
    padding-right: 50px;
    justify-content: center;
    border: 2px solid rgb(204, 204, 204);
    border-radius: 20px;
    transition: 0.5s;
}

.poster:hover{
    box-shadow: 8px 8px 8px black;
    transform: scale(1.2);
}

.blueBadge{
    background-color: rgb(231, 231, 231);
    -webkit-text-fill-color: rgb(231, 231, 231);
    border-radius: 13px;
}

.blue{
    background-color: #2b478b;
    border-color: #2b478b;
    -webkit-text-fill-color: rgb(231, 231, 231);
}

.submit{
        background-color: darkorange;
        -webkit-text-fill-color: white;
        width:100%;
        border-radius: 50px;
}

</style>











