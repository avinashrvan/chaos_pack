<template>
    <footer>
        <a class="footer" href="https://monkeytype.com/" target="_blank" rel="noopener noreferrer">
            <strong> &copy; Chaos Pack Challenge 2021 </strong> 
        </a>
        


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
        font-size: 70%;
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

    a:link, a:visited {
        color: darkblue;
    }

</style>