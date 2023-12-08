<template>
    <div>
        <div class="hidden">space</div>
        <div class="hidden">space</div>
        <h3 style="color:#00008B; font-family: Helvetica"><strong>Pricing</strong></h3>
        <h6><em>The Best Deals All Day Everyday</em></h6>
        <div class="hidden">space</div>
        <div class="hidden">space</div>

        <b-container class="b-container">
            <b-row align-v="start">
                <b-col class='col'>
                    <div class="container">
                        <PriceCard 
                            title="Free"
                            forWho="Students"
                            price="$ 0"
                            :features="['100GB Storage',
                                        '100GB Storage',
                                        '100GB Storage']"
                        />
                    </div>
                </b-col>
                    
                <b-col class='col'>
                    <div class="container">
                        <PriceCard 
                            title="Pro"
                            forWho="Professionals"
                            price="$ 10/mth"
                            :features="['100GB Storage',
                                        '100GB Storage',
                                        '100GB Storage']"
                        />
                    </div>
                </b-col>

                <b-col class='col'>
                    <div class="container">
                        <PriceCard
                            title="Premium"
                            :blue="true"
                            forWho="Absolute Saving Gurus"
                            price="$ 200/mth"
                            :features="['$20 Cashback every month', 
                                        'Unlimited storage', 
                                        'Spending Analytics']"
                        />
                    </div>
                </b-col>

            </b-row>
        </b-container>

        

    </div>
</template>


<script>
import PriceCard from './PriceCard.vue'

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