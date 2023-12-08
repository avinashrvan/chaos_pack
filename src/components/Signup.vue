<template>
    <div class="">
        <b-button   
            class="b-button open" 
            v-b-modal.modal-prevent-closing-signup pill 
            v-b-popover.hover.top="'Make one now!'" 
            title="Don't have an account yet?"
        >Signup</b-button>


        <b-modal
        id="modal-prevent-closing-signup"
        ref="modal"
        title="Register here now!"
        
        @show="resetModal"
        @hidden="resetModal"
        @ok="handleOk"
        >


        <form ref="form" @submit.stop.prevent="handleSubmit">
            <b-form-group
                label="Name"
                label-for="name-input"
                invalid-feedback="Name is required"
                valid-feedback="What a wonderful name!"
                :state="nameState"
            >
            <b-form-input
                @keyup="checkFormValidity()"
                id="name-input"
                v-model="name"
                :state="nameState"
                required
            ></b-form-input>
            </b-form-group>

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

                <b-input-group-append class="img">
                    <img v-if="showPassword" src="../assets/showPassword.png" @click="viewPassword()" width=60%>
                    <img v-if="!showPassword" src="../assets/hidePassword.png" @click="viewPassword()" width=70%>
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
        name: '',
        nameState: null,
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
            // check empty name
            this.nameState = (this.name!=='')

            // now check that the email has @ and it has characters after that
            this.emailState = ( this.email.includes('@') && 
                                this.email.slice(this.email.indexOf('@') + 1).length > 0 &&
                                this.email.indexOf('@') != 0)

            // check for password not empty
            this.passwordState = (this.password!=='')

            return this.nameState && this.emailState && this.passwordState 
        },
        resetModal() {
            this.name = '',
            this.nameState = null,
            this.email = ''
            this.emailState = null
            this.password = ''
            this.passwordState = null
            this.showPassword = false
        },
        handleOk(bvModalEvent) {
            // Prevent modal from closing
            bvModalEvent.preventDefault()
            // Trigger submit handler
            this.handleSubmit()
        },
        handleSubmit() {

            // Exit when the form isn't valid
            if (!this.checkFormValidity()) {
            return
            }

            // Hide the modal manually
            this.$nextTick(() => {
            this.$bvModal.hide('modal-prevent-closing-signup')
            })

            // randomly decide if the user can register :)
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
            this.$bvToast.toast(`Welcome, ${this.name}`,
            {
            title: 'Successful registration',
            autoHideDelay: 5000,
            appendToast: append,
            enableHtml: true,
            progressBar: true,
            solid: true,
            variant: 'success'
            })
        },
        makeBurntToast(append = true){
            this.$bvToast.toast(`Sorry, ${this.name}, the server is down. Please try later.`,
            {
            title: 'Unsuccessful registration',
            autoHideDelay: 5000,
            appendToast: append,
            enableHtml: true,
            progressBar: true,
            solid: true,
            variant: 'danger'
            })
        }
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