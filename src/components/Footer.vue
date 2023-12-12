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
    .footer{
        /* display: flex; */
        justify-content: space-between;
        align-items: center;
        margin-left: 30px;
        margin-right: 30px;
        margin-bottom: 20px;
        margin-top: 20px;
        font-size: 80%;
        -webkit-text-fill-color: darkblue;
        transition: 0.5s;
    }

    footer{
        justify-content: space-between;
        align-items: center;
        margin-left: 30px;
        margin-right: 30px;
        margin-bottom: 20px;
        margin-top: 20px;
        -webkit-text-fill-color: darkblue;
    }

    img{
        /* display: flex; */
        max-width: 60px;
        max-height: 60px;

    }

    @media (hover: hover){
        .footer:hover{
        box-shadow: 2px 2px 2px darkorange;
        transform: scale(1.2);
        font-size: 90%;
        }
    }

    .header{
        align-content: center;
    }

    a:link, a:visited {
        color: darkblue;
    }

</style>yle>