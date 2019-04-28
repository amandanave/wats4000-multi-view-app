<template>
  <div class="home">
    <div class="form-container" v-show="showForm">
      <h1>Join the Web Developers Club!</h1>
      <p>Sign up to access our special, secret page. Just create an account and answer a brief survey.</p>

      <!-- Added an HTML element to display an error message for when the user submits invalid information.  -->
      <p class="error" v-show="showError"> Please check the information you have entered. Be sure to fill in all fields.</p>
      
      <!-- Added v-on directive to let the validateForm method handle this form when it is submitted -->
      <form v-on:submit.prevent="validateForm">

        <!-- Added username field. -->
        <p>
          <label for="username">Username
            <input type="text" id="username" v-model="username">
          </label>
        </p>

        <!-- Added an email field. -->
        <p>
          <label for="email">Email
            <input type="email" id="email" v-model="email">
          </label>
        </p>

        <!-- Added a password field. -->
        <p>
          <label for="password">Password
            <input type="password" id="password" v-model="password">
          </label>
        </p>

        <!-- Added a passwordVerify field. -->
        <p>
          <label for="passwordVerify">Verify Password
            <input type="password" id="passwordVerify" v-model="passwordVerify">
          </label>
        </p>

        <p><input type="submit" value="Submit"></p>
      </form>
    </div>
    <div class="success-message" v-show="!showForm"><!-- TODO: Modulate display of the .success-message using v-show and the showForm variable. -->
      <h1>Thank you for signing up!</h1>
      <p>Please take our new member survey. Click here</p><!-- TODO: Link "Click here" to the survey page. -->
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data () {
    return {
      username: '',
      email: '',
      password: '',
      passwordVerify: '',
      showForm: true,
      showError: false
    }
  },
  methods: {
    validateForm: function () {
      // Validate the form by checking the following values:
      // username must not be blank
      // email must not be blank
      // password and passwordVerify must be equal
      //
      // When the form is validated, show the .success-message content
      // If the form is invalid, show the form error message
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.error {
  border: 1px solid #aa0000;
  padding: 1rem;
  color: #aa0000;
}
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
