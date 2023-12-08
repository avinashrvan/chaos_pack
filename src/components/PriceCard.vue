<template>
    <div id="main">

        <!-- CODE FOR ALL CARDS -->
        <div :class="blue ? 'bluePoster poster shadow' : 'poster shadow'">

            <!-- DECIDE ON THE TEXT STYLE BASED ON THE CARD TYPE -->
            <h5  :class="blue ? 'bluePosterText' : 'whitePosterText'"><strong>{{ title }}</strong></h5>
            <h6 :class="blue ? 'bluePosterText': null">For {{ forWho }}</h6>

            <div class="hidden">space</div>

            <h1 :class="blue ? 'bluePosterText' : 'whitePosterText'"><strong>{{ price }}</strong></h1>

            <div class="hidden">space</div>

            <!-- FOR ALL FEATURES, WE LIST IT OUT  -->
            <ul class="list-group list-group-flush">
                <li :class="blue ? 'list-group-item d-flex bluePoster' : 'list-group-item d-flex'">
                    <b-badge pill variant="danger" :class="blue ? 'whiteBadge' : 'badge'">ii</b-badge>
                    <div class="hidden">ss</div>
                    <strong>{{ sp1 }}</strong></li>
                <li :class="blue ? 'list-group-item d-flex bluePoster' : 'list-group-item d-flex'">
                    <b-badge pill variant="danger" :class="blue ? 'whiteBadge' : 'badge'">ii</b-badge>
                    <div class="hidden">ss</div>
                    <strong>{{ sp2 }}</strong></li>
                <li :class="blue ? 'list-group-item d-flex bluePoster' : 'list-group-item d-flex'">
                    <b-badge pill variant="danger" :class="blue ? 'whiteBadge' : 'badge'">ii</b-badge>
                    <div class="hidden">ss</div>
                    <strong>{{ sp3 }}</strong></li>
            </ul>

            <div class="hidden">y</div>
            <div class="hidden">y</div>

            <!-- Add one extra space if this is the premium card -->
            <div class="hidden" v-if="blue">y</div>

            <!-- CREATE THE BUTTON TO POP OPEN THE MODAL -->
            <b-button class="submit" @click="openModal(title)">GET STARTED</b-button>
            <ModalForm :initial="title"/>
            

        </div>
        
    
        <div class="hidden">y</div>
        <div class="hidden">y</div>

    </div>
</template>



<script>
import ModalForm from './ModalForm.vue'

export default {
    name: "PriceCard",
    components:{
        ModalForm,
    },
    props:{
        title: String,
        forWho: String,
        price: String,
        pointColor: String,
        sp1: String,
        sp2: String,
        sp3: String,
        blue: {type: Boolean, default: false}
    },
    methods:{
        openModal(modalId){
            this.$bvModal.show(modalId)
        }
    }
}
</script>



<style scoped>
.list-group-item {
    border-color: white;
}

.whitePosterText{
    color:#00008B; 
    font-family: Helvetica;
}

.bluePosterText{
    color:rgb(231, 231, 231); 
    font-family: Helvetica;
}


.badge{
    background-color: darkblue;
    -webkit-text-fill-color: darkblue;
    border-radius: 13px;
    max-height: 22px;
}

.whiteBadge{
    background-color: rgb(231, 231, 231);
    -webkit-text-fill-color: rgb(231, 231, 231);
    border-radius: 13px;
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

.bluePoster{
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











