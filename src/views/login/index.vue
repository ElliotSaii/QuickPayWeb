<template>
    <div class="login_container">
        
        <v-sheet class="login_form mt-0 mx-auto" width="380">
            <v-form fast-fail @submit.prevent>
        
                <v-otp-input :length="6" model-value="333" variant="solo-filled" error></v-otp-input>

                <v-btn class="mt-2" type="submit"  onclick="getOtpCode()" block>Login with SMS</v-btn>
               
            </v-form>
        </v-sheet>
    </div>
</template>
<script>
  export default {
    data: () => ({
      otpCode: '',
      otpCodeRules: [
        value => {
            if(/^\d{6}$/.test(value)) return true
            return 'Otp code is not valid'
        }
      ]
    }),
    methods: {
        getOtpCode(){
            alert('3')
        }
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
    filter: drop-shadow(0 0 2em #121643);
}

</style>
