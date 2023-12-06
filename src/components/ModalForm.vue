<template>
  <div>
    <b-button v-b-modal.modal-prevent-closing>Open Modal</b-button>

    <b-modal
      id="modal-prevent-closing"
      ref="modal"
      title="Submit Your Details"
      
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
            id="email-input"
            v-model="email"
            type="email"
            :state="emailState"
            required
          ></b-form-input>
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
        name: '',
        nameState: null,
        email: '',
        emailState: null
      }
    },
    methods: {
      checkFormValidity() {
        const valid = this.$refs.form.checkValidity()
        this.nameState = valid
        this.emailState = valid
        return valid
      },
      resetModal() {
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
          this.$bvModal.hide('modal-prevent-closing')
        })

        // Give a confirmation message to the user
        alert("\nThank you for registering your email!: \n".concat(this.name, this.email))

        
      }
    }
  }
</script>