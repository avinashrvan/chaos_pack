<template>
  <div>
    <b-button class="open" v-b-modal.modal-prevent-closing-free @click="setSelected(initial)">GET STARTED</b-button>

    <b-modal
      id="modal-prevent-closing-free"
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
            @keypress="checkFormValidity()"
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
            @keypress="checkFormValidity()"
            id="email-input"
            v-model="email"
            type="email"
            :state="emailState"
            required
          ></b-form-input>
        </b-form-group>

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
        name: '',
        nameState: null,
        email: '',
        emailState: null,
        selected: "Free",
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
        },
        checkFormValidity() {
            const valid = false

            // first we check that the name is not empty
            this.nameState = (this.name != '')

            // now check that the email has @ and it has characters after that
            this.emailState = (this.email.includes('@') && this.email.slice(this.email.indexOf('@') + 1).length > 0)

            return this.nameState && this.emailState
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
            this.$bvModal.hide('modal-prevent-closing-free')
            })

            // Give a confirmation message to the user
            this.makeToast()
            
        },
        makeToast(append = true) {
            this.$bvToast.toast(`Thank you, ${this.name}! ${this.email} is now registered for the ${this.selected} package`,
            {
            title: 'Thank you for registering!',
            autoHideDelay: 5000,
            appendToast: append,
            enableHtml: true,
            progressBar: true
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