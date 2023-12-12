<template>
    <div class="">
        <b-button 
            id='login'
            class="b-button open" 
            v-b-modal.modal-prevent-closing-login pill
            
        >Login</b-button>
        <b-popover 
            target="login" 
            triggers="hover" 
            placement="top"
            title="Already have an account?"
            :disabled = windowWidth>
            Login now!</b-popover>


        <b-modal
        id="modal-prevent-closing-login"
        ref="modal"
        title="Welcome back!"
        
        @show="resetModal"
        @hidden="resetModal"
        @ok="handleOk"
        >


        <form ref="form" @submit.stop.prevent="handleSubmit">
            <b-form-group
            label="Email"
            label-for="email-input"
            invalid-feedback="Your email is invalid"
            valid-feedback="Fantastic email!"
            :state="emailState"
            >
            <b-form-input
                @keyup="checkFormValidity()"
                id="email-input"
                v-model="email"
                type="email"
                placeholder="Enter your email"
                :state="emailState"
                required
            ></b-form-input>
            </b-form-group>

            <b-form-group
                label="Password"
                label-for="passwordEntry"
                invalid-feedback="Your password can't be empty"
                valid-feedback="Nice password"
                :state="passwordState"
            >

            <b-input-group>
            <b-form-input 
                @keyup="checkFormValidity()"
                :type="showPassword ? 'text' : 'password'" 
                class="form-control" 
                id="passwordEntry" 
                placeholder="Password"
                :state="passwordState"
                v-model="password"></b-form-input>

                <b-input-group-append>
                    <img class="img" v-if="showPassword" src="../assets/showPassword.png" @click="viewPassword()" width=40%>
                    <img class="img" v-if="!showPassword" src="../assets/hidePassword.png" @click="viewPassword()" width=50%>
                </b-input-group-append>

            </b-input-group>
            </b-form-group>

            

            



            
        </form>
        </b-modal>

    </div>
</template>



<script>
export default {
    name: "Login",
    data() {
      return {
        email: '',
        emailState: null,
        password: '',
        passwordState: null,
        showPassword: false
      }
    },
    props: {
        
    },
    methods: {
        checkFormValidity() {
            // now check that the email has @ and it has characters after that
            this.emailState = ( this.email.includes('@') && 
                                this.email.slice(this.email.indexOf('@') + 1).length > 0 &&
                                this.email.indexOf('@') != 0)

            // check for password not empty
            this.passwordState = (this.password!=='')

            return this.emailState && this.passwordState
        },
        resetModal() {
            this.email = ''
            this.emailState = null
            this.password = ''
            this.passwordState = null
            this.show = null,
            this.showPassword = false
        },
        handleOk(bvModalEvent) {
            // Prevent modal from closing
            bvModalEvent.preventDefault()
            // Trigger submit handler
            this.handleSubmit()
        },
        handleSubmit() {
            // do a short load
            this.show = true

            // Exit when the form isn't valid
            if (!this.checkFormValidity()) {
            return
            }

            // Hide the modal manually
            this.$nextTick(() => {
            this.$bvModal.hide('modal-prevent-closing-login')
            })

            // randomly decide if they can log in :)
            const choice = Math.floor(Math.random() * 2);

            if(choice==0){
                this.makeGoodToast()
            } else{
                this.makeBurntToast()
            }
            

            
        },
        viewPassword(){
            this.showPassword = !this.showPassword
        },
        makeGoodToast(append = true) {
            this.$bvToast.toast(`Sorry, that account does not exist!`,
            {
            title: 'Unsuccessful login',
            autoHideDelay: 5000,
            appendToast: append,
            enableHtml: true,
            progressBar: true,
            solid: true,
            variant: 'danger'
            })
        },
        makeBurntToast(append = true) {
            this.$bvToast.toast(`Welcome back, ${this.email}`,
            {
            title: 'Successful login',
            autoHideDelay: 5000,
            appendToast: append,
            enableHtml: true,
            progressBar: true,
            solid: true,
            variant: 'success'
            })
        }
    },
    computed: {
        windowWidth: function() {
            return window.innerWidth < 500}
    }
}
</script>



<style scoped>
.b-button{
    background-color: darkorange;
    -webkit-text-fill-color: white;
}

.img{
    margin-left: 20px;
}
</style>