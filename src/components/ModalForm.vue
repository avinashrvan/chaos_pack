<template>
  <div>
    <b-modal
      :id="initial"
      ref="modal"
      title="Submit Your Details"
      
      @show="resetModal(initial)"
      @hidden="resetModal"
      @ok="handleOk"
    >

      <!-- start of the form for the user to fill up -->
      <form ref="form" @submit.stop.prevent="handleSubmit">

        <!-- user's name input group -->
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

        <!-- user's email input group -->
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
            :state="emailState"
            required
          ></b-form-input>
        </b-form-group>

        <!-- user's required package input group -->
        <b-form-group
          label="Package"
          :state="true"
        >
          <b-form-select 
            v-model="selected" 
            :options="options"
            
        ></b-form-select>
        </b-form-group>




        
      </form>
    </b-modal>
  </div>
</template>

<script>
  export default {
    name:"ModalForm",
    data() {
      return {
        modalType: '',
        name: '',
        nameState: null,
        email: '',
        emailState: null,
        selected: null,
        options: [
          { value: 'Free', text: 'Free - For Students' },
          { value: 'Pro', text: 'Pro - For Professionals' },
          { value: 'Premium', text: 'Premium - For Absolute Saving Gurus' },
        ]
      }
    },
    props: {
        initial: String
    },
    methods: {
        setSelected(initial){
            this.selected = initial
            this.modalType = initial
        },
        checkFormValidity() {
            // first we check that the name is not empty
            this.nameState = (this.name != '')

            // now check that the email has @ and it has characters after that
            this.emailState = (this.email.includes('@') && this.email.slice(this.email.indexOf('@') + 1).length > 0)

            return this.nameState && this.emailState
        },
        resetModal(initial) {
            this.setSelected(initial)
            this.name = ''
            this.nameState = null
            this.email = ''
            this.emailState = null
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
            this.$bvModal.hide(this.modalType)
            })

            // Give a confirmation message to the user
            this.makeToast()
            
        },
        makeToast(append = false) {
            this.$bvToast.toast(`Thank you, ${this.name}! ${this.email} is now registered for the ${this.selected} package`,
            {
            title: 'Thank you for registering!',
            autoHideDelay: 5000,
            appendToast: append,
            enableHtml: true,
            progressBar: true,
            solid: true,
            variant: 'success'
            })
        }
    }
  }
</script>


<style scoped>
.open{
        background-color: darkorange;
        -webkit-text-fill-color: white;
        width:100%;
        border-radius: 50px;
}
</style>