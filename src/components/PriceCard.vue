<template>
    <div>

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
                    {{ sp1 }}</li>
                <li class="list-group-item d-flex ">
                    <b-badge pill variant="danger" class="badge">ii</b-badge>
                    <div class="hidden">ss</div>
                    {{ sp2 }}</li>
                <li class="list-group-item d-flex ">
                    <b-badge pill variant="danger" class="badge">ii</b-badge>
                    <div class="hidden">ss</div>
                    {{ sp3 }}</li>
            </ul>

            <div class="hidden">y</div>
            <div class="hidden">y</div>
            <div>GET STARTED</div>

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
                    {{ sp1 }}</li>
                <li class="list-group-item d-flex blue">
                    <b-badge pill variant="danger" class="blueBadge">ii</b-badge>
                    <div class="hidden">ss</div>
                    {{ sp2 }}</li>
                <li class="list-group-item d-flex blue">
                    <b-badge pill variant="danger" class="blueBadge">ii</b-badge>
                    <div class="hidden">ss</div>
                    {{ sp3 }}</li>
            </ul>

            <div class="hidden">y</div>
            <div class="hidden">y</div>
            <div class="hidden">y</div>
            <div class="hidden">y</div>

            <div>GET STARTED</div>

        </div>






    </div>
</template>



<script>
export default {
    name: "PriceCard",
    components:{},
    props:{
        title: String,
        forWho: String,
        price: String,
        pointColor: String,
        sp1: String,
        sp2: String,
        sp3: String

    },
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
}

.poster{
    align-content: left;
    text-align: left;
    padding: 40px;
    justify-content: center;
    border-radius: 20px;
}

.blueBadge{
    background-color: rgb(231, 231, 231);
    -webkit-text-fill-color: rgb(231, 231, 231);
    border-radius: 13px;
}

.blue{
    background-color: darkblue;
    border-color: darkblue;
    -webkit-text-fill-color: rgb(231, 231, 231);
}
</style>











