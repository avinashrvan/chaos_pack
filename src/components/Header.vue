<template>
    <header>
        <h6>{{ title }}</h6>

        <img src="../assets/logo.png" alt="">

        <h6>SIGN UP || LOGIN</h6>

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
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-left: 30px;
        margin-right: 30px;
        margin-bottom: 20px;
        margin-top: 20px;
    }

    img{
        display: flex;
        width: 40px;
        height: 40px;

    }

</style>