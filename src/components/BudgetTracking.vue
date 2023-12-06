<template>
<div class="budget">
    <h3 class="hidden">space</h3>
    <h3 style="color:#00008B; font-family: Helvetica" ><strong>Budget Tracking Made Easy</strong></h3>

    <b-container class="b-container" >
            <b-row>
                <b-col class='col'>
                    <img src="../assets/savings.png" class="img-responsive" width="40%"> 
                    <h5 class="title">Maximize your</h5>
                    <h3 class="bold">Savings</h3>
                    <p class="text">Lorem Ipsum Dolor Sit Amet, Consectetur Adipiscing Elit. Morbi Quis Lectus Sed Sapien Porta Elementum</p>               
                </b-col>

                <b-col class='col'>
                    <img src="../assets/performance.png" class="img-responsive" width="40%">
                    <h5 class="title">Track your</h5>
                    <h3 class="bold">Performance</h3>
                    <p class="text">Lorem Ipsum Dolor Sit Amet, Consectetur Adipiscing Elit. Morbi Quis Lectus Sed Sapien Porta Elementum</p>

                </b-col>

                <b-col class='col'>
                    <img src="../assets/winner.png" class="img-responsive" width="40%">
                    <h5 class="title">Feel like a</h5>
                    <h3 class="bold">Winner</h3>
                    <p class="text">Lorem Ipsum Dolor Sit Amet, Consectetur Adipiscing Elit. Morbi Quis Lectus Sed Sapien Porta Elementum</p>                
                </b-col>
            </b-row>
    </b-container>  
    <h3 class="hidden">space</h3> 

    
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

    .bold{
        font-family:'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        -webkit-text-fill-color: #f77d48;
        margin-top: 10px;
    }

    .text{
        margin-top: 10px;
        font-size: 90%;
        
    }

    .col{
        margin-left: 50px;
        margin-right: 50px;        
    }

    


</style>