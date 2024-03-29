<template>
    <div class="login_container">
        <v-sheet class="login_form mt-0 mx-auto" width="380">
            <v-form fast-fail @submit.prevent>
                <v-text-field v-model="firstName" :rules="firstNameRules" label="First name"></v-text-field>

                <v-text-field v-model="lastName" :rules="lastNameRules" label="Last name"></v-text-field>
                <v-text-field v-model="phoneNumber" :rules="phoneNumberRules" label="Phone No"></v-text-field>

                <v-row> 
                  <v-col class="d-flex child-flex" cols="8"> 
                    <v-text-field v-model="captchaCode" :rules="captchaCodeRules"  label="Enter Code"></v-text-field>
                  </v-col>
                   <img src="" alt="captcha" @click="getCaptchaCode()">
                </v-row>
                <v-btn class="mt-2" type="submit" block>Submit</v-btn>
                <div style="margin-top: 10px; ">Already have an account? <a href="/login" style="color: white">Login</a></div>
            </v-form>
        </v-sheet>
    </div>
</template>
<script>
  export default {
    data: () => ({
      firstName: '',
      firstNameRules: [
        value => {
          if (value?.length > 1) return true

          return 'First name is required'
        },
      ],
      lastName: '',
      lastNameRules: [
        value => {
          if (/[^0-9]/.test(value)) return true

          return 'Last name is required'
        },
      ],
      phoneNumber: '',
      phoneNumberRules: [
        value => {
            if(/[0-9]/.test(value)) return true
            return 'Phone number is not valid'
        }
      ],
      captchaCode: '',
      captchaCodeRules: [
         value => {
            if(/^[a-zA-Z0-9]{6}$/.test(value)) return true
            return 'Invalid captcha code'
         }

      ]
    }),
    methods: {
      getCaptchaCode(){
        console.log("ieiiei")
      }
    },
    created() {
      this.getCaptchaCode();
    }
  }
</script>
<style scoped>
.login_container {
    height: 100vh;
    background: url('@/assets/login_images/login_bg3.jpg') center center fixed no-repeat;
    background-size: cover;
   
    
}

.login_form {
 
    max-width: 100vw;
    padding: 4.5vh;
    margin: calc((100vh - 475px) / 2) 5vw 5vw;
    overflow: hidden;
    background: url('~@/assets/login_images/login_form_bg.png');
    background-size: 100% 100%;
    color: #fff;
    will-change: filter;
    transition: filter 300ms;
    
    
}

.login_form:hover { 
    filter: drop-shadow(0 0 2em #6e1a3b);
}

</style>
