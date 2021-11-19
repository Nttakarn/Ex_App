<template>
  <v-parallax
    dark
    src="https://images.app.goo.gl/jRKPcDT9sAeVFVkT9"
    class="rr"
    height="568"
  >
    <v-row
      align="center"
      justify="center"
      class="ss"
    >
      <v-col
        class="text-center"
        cols="10"
      >
        <p class="text-h8 font-weight-thin mb-4" style="margin-top:-20px;">
          <br>Sign up your bank account
        </p>
        <v-form ref="form" lazy-validation class="aa">
          <v-text-field
            v-model="name"
            :counter="10"
            label="Name"
            required
          />

          <v-text-field label="Bank Account" class="q" required />
          <v-text-field label="Mobiless phone number" class="q" required />
          <v-text-field label="E-mail" class="q" required />

          <v-text-field
            v-model="password"
            :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
            :rules="[rules.required, rules.min]"
            :type="show1 ? 'text' : 'password'"
            name="input-10-1"
            label="Normal with hint text"
            hint="At least 8 characters"
            counter
            class="pp"
            @click:append="show1 = !show1"
          />
          <v-checkbox
            :rules="[v => !!v || 'You must agree to continue!']"
            label="By signing up, you agree to Bank's Term of Use &amp; Privacy Policy."
            required
          />
          <v-row class="d-flex justify-center ">
            <v-btn color="warning" class="mr-4">
              SIGN UP
            </v-btn><p>or</p>&nbsp;&nbsp;&nbsp;
            <v-btn
              color="error"
              class="mr-4"
              @click="reset"
            >
              CANCEL
            </v-btn>
          </v-row>
        </v-form>
      </v-col>
      <v-col>
        <h5 style="margin-top:-50px;">
          <br>
          Already signed up? <router-link :to="{name: 'index'}" class="nav-link">
            Login
          </router-link>
        </h5>
      </v-col>
    </v-row>
  </v-parallax>
</template>
<script>
export default {
  data () {
    return {
      show1: false,
      show2: true,
      show3: false,
      show4: false,
      password: 'Password',
      rules: {
        required: value => !!value || 'Required.',
        min: v => v.length >= 8 || 'Min 8 characters',
        emailMatch: () => ('The email and password you entered don\'t match')
      }
    }
  }
}
</script>

<style>
  .aa{
    margin-top: -15px;
  }
  .q{
    margin-top: -23px;
  }
  .rr{
    margin-top: 20px;
    font-size: 13px;
  }
  .ss{
    border-radius: 30px;
    margin-top: 5px;
    margin-left: -5px;
    margin-right: -5px;
    margin-bottom: 50px;
    background-color: rgb(39, 39, 39);
    font-size: 15px;
  }
 .v-input .v-label {
    font-size: 0.7em;
    color: rgb(255, 255, 255);
}
</style>
