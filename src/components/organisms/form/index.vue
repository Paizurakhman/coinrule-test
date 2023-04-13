<template>
<div class="login">
  <div class="login__card">
    <h2>Account Login</h2>
    <form>
      <TextField label="Email" v-model="authState.login" />
      <TextField type="password" label="Password" v-model="authState.password" />
      <div class="login__action">
        <base-button append-icon="play" variant="danger">Log In</base-button>
      </div>
      <div class="login__action">
        <p>or log in with</p>
        <base-button
            class="btn"
            prepend-icon="google"
            variant="outlined_gray"
            href="google.com"
        >Google</base-button>

        <base-button
            class="btn"
            prepend-icon="facebook"
            variant="outlined_gray"
            href="facebook.com"
        >Facebook</base-button>

      </div>
    </form>
  </div>
</div>
</template>

<script>
import TextField from "@/components/atoms/text-field/index.vue";
import BaseButton from "@/components/atoms/base-button/index.vue";
import {reactive} from "vue";

export default {
  name: "LoginForm",
  components: {BaseButton, TextField},
  setup() {
    const authState = reactive({
      login: '',
      password: ''
    })

    return { authState }
  }
}
</script>

<style scoped lang="scss">
.login {
  max-width: 550px;
  margin: 0 auto;
  $self: &;
  &__card {
    min-height: 300px;
    background: #FFFFFF;
    box-shadow: 0 10px 16px rgba(0, 0, 0, 0.24);
    border-radius: 8px;
    padding: 60px 70px 40px;
    margin: 40px 0;
    h2 {
      font-weight: 700;
      font-size: 35px;
      line-height: 37px;
      text-align: center;

      color: #000000;
      margin-bottom: 24px;
    }
  }

  &__action {
    text-align: center;
    padding-top: 35px;
    margin-bottom: 20px;
    & + #{ $self }__action {
      border-top: 1px solid rgba(0, 0, 0, 0.12);
      margin-bottom: 0;
    }

    p {
      font-weight: 600;
      font-size: 15px;
      line-height: 22px;
      text-align: center;
      color: #000000;
      margin-bottom: 18px;
    }

    .btn {
      & + .btn {
        margin-left: 11px;
      }
    }
  }
  @media screen and (max-width: 767px){
    &__card
    {
      border-radius: 0;
      margin-top: 0;
      padding-left: 20px;
      padding-right: 20px;
      h2 {
        font-size: 29px;
        line-height: 30px;
      }
    }
  }
}
</style>