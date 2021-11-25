<template>
  <div class="register-form">
    <div class="back">
      <img src="@/assets/images/back.png" />
      <span>Back</span>
    </div>
    <div class="content">
      <div class="header">
        <h3>Start from free</h3>
        <h1>Create an account</h1>
      </div>
      <div class="sign-up">
        <!-- <img src="@/assets/images/google.svg" alt="Google" /> -->
        <Button icon="@/assets/images/google.svg" alt="Google"
          >Sign Up with Google</Button
        >
        <Button>Sign Up with Facebook</Button>
      </div>
      <div class="form">
        <div class="email-registration">
          <hr class="line" />
          <span>Or use your email for registration</span>
        </div>

        <Form />
      </div>
      <div class="account">
        Already have an account? <span class="login">Login</span>
      </div>
    </div>
  </div>
</template>

<script>
import Button from "@/components/button.vue";
import Form from "@/components/form.vue";
export default {
  name: "Register",
  components: {
    Button,
    Form,
  },
};
</script>

<style scoped>
.register-form {
  position: relative;
  background: #fff;
  width: 500px;
  height: auto;
  border-radius: 30px;
  box-shadow: 0px 6px 15px rgba(60, 113, 255, 0.4);
}
.back {
  position: absolute;
  top: 15px;
  left: 20px;
  display: flex;
  align-items: center;
}
.back span {
  margin-left: 5px;
}
.content {
  margin: 50px;
}
/* .sign-up {
  display: flex;
  justify-content: space-between;
} */
.sign-up {
  display: grid;
  grid-template-columns: auto auto;
  grid-gap: 20px;
  height: 48px;
}
/* email-reg */
.email-registration {
  position: relative;
  margin: 30px 0;
}
.email-registration span {
  position: absolute;
  top: -8px;
  background: #fff;
  padding-right: 5px;
}
hr.line {
  border: 1px solid #000;

  width: 100%;
}
/* button login */
.account {
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 12px;
  margin-top: 10px;
  color: #757575;
}
.account span.login {
  font-size: 14px;
  font-weight: 600;
  color: #3c71ff;
  margin-left: 3px;
}
@media only screen and (max-width: 736px) {
  .register-form[data-v-8f8a1d9a] {
    position: relative;
    background: #fff;
    width: 100%;
    height: 100vh;
    border-radius: unset;
  }
  .content {
    margin: 50px 20px;
  }
}
</style>