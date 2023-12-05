<template>
    <header>
        <h5>{{ title }}</h5>
        <div class="box"> 
            <img src="../assets/diamond_logo.png"  alt="Example image"/> 
        </div>
        <h6>LOGIN || SIGNUP</h6>
    </header>

</template>



<script>
export default{
    name: 'Header',
    props: {
        title: String,

    },
}
</script>



<style scoped>
    header{
        display:flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 20px;
        margin-block-end: 20px;
        margin-right: 30px;
        margin-left: 30px;
    }

    .box {
    width: 22px;
    height: 22px;
    }

    img {
    width: 100%; /* takes the 100 % width of its container (.box div)*/
    height: 100%; /* takes the 100 % height of its container (.box div)*/
    }
</style>