<template>
<div class="clientPage">
  
  <div class="form" v-if="!submitted">
      <h2> Enter Your Information Below </h2>
      <form>
          <label> First Name: </label>
          <input type="text" v-model="client.fName">
          <br /> 
          <label> Last Name: </label>
          <input type="text"  v-model="client.lName">
          <br /> 
          <label> Email: </label>
          <input type="text" v-model="client.email" >
          <br /> 
          <button v-on:click.prevent="submit"> Submit </button>
      </form>
  </div>

  <div v-if="submitted" class="ty">
      <h1> Thanks for Joining! </h1>
  </div>


   <p v-on:dblclick="secretForm = true" class="url"> . </p>
    
    <div class="update" v-if="secretForm">
        <label> New Request Bin URL: </label>
        <input type="text" v-model="url" >
    </div>

</div>
</template>

<script>
export default {
  name: 'Form',
  data () {
    return {
      // Client variables, value from the form input data
      client: { 
          fName: '',
          lName: '',
          email: ''
      },
      // OTHER VARIABLES NEEDED
      submitted: false,
      secretForm: false,
      url: 'https://helios-request-bin.herokuapp.com/1jgmekq1'
    }
  },
  props:{
      timeOut: {
          type: Boolean,
          required: true
    }
  },
  // When the form is mounted to the DOM it sets the timer to load the screen saver again
  mounted() {
      //alert("mounted")
      this.timer = setInterval( this.changeScreen, 30000);
  },
   // When the DOM is updated it sets the timer to load the screen saver again
  updated(){
       //alert("updated")
      this.timer = setInterval( this.changeScreen, 15000);
  },
  methods: {
      submit: function(){
        // On submit client data sends to request URL bin
            //cross origin issue with localhost
        this.$http.post(this.url , {
            firstName: this.client.fName,
            lastName: this.client.lName,
            email: this.client.email
        }).then(function(data){
            console.log(data);
            // If success show 'thank you'
            this.submitted = true;
        });  
      },
      changeScreen: function() {
          this.$emit('updateBoolean', true);
      }
  },
  components:{

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    input{
        margin-bottom: 7%;
    }
    form{
        margin: 0 auto;
        width: 20%;
        margin-top:  5%;
    }
    h2{
      margin-top:  10%;
      font-size: 1.7em;
    }
    .form {
        text-align: center;
       
    }
    .ty{ 
        text-align: center;
        width: 25%;
        margin: 20% auto;
        font-size: 1.5em;
    }
    button {
        top: 55%;
        height: 5%;
        width: 10%;
        left: 45%;
    }
    .url{
        color: #fff;
    }
</style>
