<template>
    <div>
        <h3 style="color:#00008B; font-family: Helvetica"><strong>Pricing</strong></h3>
        <h6><em>The Best Deals All Day Everyday</em></h6>

        <b-container class="b-container">
            <b-row align-v="center">
                <b-col class='col'>
                    <div class="container">
                        <PriceCard 
                            title="Free"
                            forWho="Students"
                            price="$ 0"
                            sp1="100GB Storage"
                            sp2="100GB Storage"
                            sp3="100GB Storage"
                        />
                    </div>
                </b-col>
                    
                <b-col class='col'>
                    <div class="container">
                        <PriceCard 
                            title="Pro"
                            forWho="Professionals"
                            price="$ 10/mth"
                            sp1="100GB Storage"
                            sp2="100GB Storage"
                            sp3="100GB Storage"
                        />
                    </div>
                </b-col>

                <b-col class='col'>
                    <div class="container">
                        <PriceCard id="premiumCard"
                            title="Premium"
                            forWho="Absolute Saving Gurus"
                            price="$ 200/mth"
                            sp1="$20 Cashback every month"
                            sp2="Unlimited storage"
                            sp3="Spending Analytics"
                        />
                    </div>
                </b-col>

            </b-row>
        </b-container>



    </div>
</template>


<script>
import PriceCard from './PriceCard.vue'
const wow = document.querySelector("premiumCard")

export default {
    name: "Pricing",
    components:{
        PriceCard,
    },
    props:{}    
}
</script>


<style scoped>

</style>