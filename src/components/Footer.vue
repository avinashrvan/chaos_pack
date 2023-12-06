<template>
    <footer>
        <h6 class="footer">
            <strong> &copy; Chaos Pack Challenge 2021 </strong> 
        </h6>
        


    </footer>
</template>


<script>


export default {
    name: 'Footer',
    props: {

    },

}
</script>


<style scoped>
    footer{
        /* display: flex; */
        justify-content: space-between;
        align-items: center;
        margin-left: 30px;
        margin-right: 30px;
        margin-bottom: 20px;
        margin-top: 20px;
        font-size: 30%;
        -webkit-text-fill-color: darkblue;
    }

    img{
        /* display: flex; */
        max-width: 60px;
        max-height: 60px;

    }

    .header{
        align-content: center;
    }

</style>