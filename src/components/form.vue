<template>
  <form>
    <div class="grid-container">
      <Input name="fname" type="text">First Name</Input>

      <Input name="lname" type="text">Last Name</Input>
    </div>
    <div class="form-control">
      <Input name="email" type="email">Email</Input>
    </div>
    <div class="form-control password">
      <Input name="password" :type="password.password">Password</Input>
      <img
        src="@/assets/images/view-hide.png"
        class="password-icon"
        alt="password"
        @click="togglePassword"
      />
    </div>

    <div class="error">
      <div class="valid">
        <div>
          <img src="@/assets/images/valid.svg" /><span class="text"
            >8 Characters min.</span
          >
        </div>
        <div>
          <img src="@/assets/images/valid.svg" /><span class="text"
            >One number</span
          >
        </div>
      </div>
    </div>
    <div class="agree">
      <input type="checkbox" id="agree" name="agree" />
      <label for="agree">
        By creating account, you agree to accept our Privacy Policy, Terms of
        Service and Notification settings.</label
      >
    </div>
    <div class="submit">
      <button class="button">Create a Free Account!</button>
    </div>
  </form>
</template>

<script>
import { computed, ref } from "vue";
import Input from "@/components/input.vue";
export default {
  name: "Form",
  components: {
    Input,
  },
  setup: () => {
    let pass = ref(true);
    const togglePassword = () => {
      pass.value = !pass.value;
    };
    const password = computed(() => {
      if (pass.value === true) {
        return {
          password: "password",
        };
      } else {
        return {
          password: "text",
        };
      }
    });
    return {
      password,
      togglePassword,
    };
  },
  // data() {
  //   return {
  //     password: null,
  //   };
  // },
};
</script>

<style scoped>
.grid-container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-gap: 20px;
}
.form {
  position: relative;
}
.agree {
  display: flex;
  align-items: center;
}
.agree label {
  margin-left: 10px;
  font-size: 12px;
}
.submit {
  margin-top: 10px;
}
.button {
  border-radius: 5px;
  background-color: #3c71ff;
  border: 0;
  color: #fff;
  padding: 13px 10px;
  width: 100%;
  text-align: center;
  text-decoration: none;
  display: block;
  font-size: 13px;
  margin: 4px 2px;
  cursor: pointer;
  outline: none;
}
/* helper */
.valid {
  display: flex;
  flex-direction: row;
  font-size: 12px;
  margin: 10px 0;
}
.valid div {
  margin: 0 10px;
  display: flex;
  align-items: center;
}
.valid span.text {
  margin-left: 5px;
}
/* password */
.form-control.password {
  position: relative;
}
img.password-icon {
  position: absolute;
  right: 10px;
  top: 50%;
  transform: translateY(-50%);
}
</style>