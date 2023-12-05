<template>
<div class="budget">
    
    <h3 style="color:#00008B; font-family: Helvetica"><strong>Budget Tracking Made Easy</strong></h3>

    <b-container class="b-container">
            <b-row>
                <b-col class='col'>
                    <img src="../assets/savings.png" class="img-responsive" width="50%"> 
                    <h5 class="title">Maximize your</h5>
                    <h3 class="bold">Savings</h3>
                    <p>Lorem Ipsum Dolor Sit Amet, Consectetur Adipiscing Elit. Morbi Quis Lectus Sed Sapien Porta Elementum</p>               
                </b-col>

                <b-col class='col'>
                    <img src="../assets/getStarted.png" class="img-responsive" width="100%">                
                </b-col>

                <b-col class='col'>
                    <img src="../assets/getStarted.png" class="img-responsive" width="100%">                
                </b-col>
            </b-row>
    </b-container>   
    
    
</div>    
</template>




<script>
export default {
    name: "BudgetTracking",
    props: {},
    components: {}, 
}


</script>



<style scoped>
    .budget{
        background-color: #f5f9fe;
    }

    .title{
        font-family:'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        -webkit-text-fill-color: grey;
        margin-top: 20px;
    }

    


</style>