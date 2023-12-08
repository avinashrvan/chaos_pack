<template>
    <div>
        <b-form class="inline" @submit="onSubmit">
                
                <b-form-input
                    id="input-1"
                    v-model="email"
                    type="email"
                    placeholder="Enter your email"
                    class="in shadow"
                    required
                ></b-form-input>
        
                <b-button 
                    pill 
                    type="" 
                    variant="light" 
                    class="submit"
                >GET STARTED</b-button>
        
        </b-form>
    </div>
</template>


<script>
export default {
    name: "InputEmail",
    data(){
        return{
            email: '',
        }
    },

    methods: {
      onSubmit(event) {
        
        event.preventDefault()
        this.$bvToast.toast(`We will send an email to you soon: ${this.email}`,
            {
            title: 'Thank you for registering!',
            autoHideDelay: 5000,
            appendToast: true,
            enableHtml: true,
            progressBar: true,
            solid: true,
            variant: 'success'
            })
        document.getElementById("input-1").value = null
      },
     
    }
  
}
</script>

<style scoped>
    .in{
        border-radius: 100px;
        border-color: black;
    }

    .submit{
        background-color: darkorange;
        -webkit-text-fill-color: white;
        min-width: 200px;
    }

    .inline{
        display:flex;
        width: auto;
    }
</style>