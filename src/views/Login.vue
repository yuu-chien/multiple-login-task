<template>
  <div>
    <section class="l-title">
      <h2 class="o-title">Choose Account Type</h2>
    </section>
    <!-- 身分選擇 -->
    <section class="l-identityCard">
      <div
        class="l-identityCard__item"
        v-for="(person, idx) in identities"
        :key="idx"
      >
        <identity-card :identity="person" :idx="idx"></identity-card>
      </div>
    </section>
    <!-- 招呼語 -->
    <section class="l-title">
      <div class="o-text">
        <p>Hello !</p>
        <p>Please full out the form below to get started</p>
      </div>
    </section>
    <!-- 登入 -->
    <section class="l-form">
      <div class="l-form__row">
        <div class="c-icobox c-icobox--email">
          <i class="c-icobox c-icobox__ico"></i>
          <input
            class="c-icobox c-icobox__inp"
            type="text"
            placeholder="Username"
            v-model="acc.username"
          />
          <label class="c-icobox c-icobox__lbl" for="">Username</label>
        </div>
      </div>
      <div class="l-form__row">
        <div class="c-icobox c-icobox--lock">
          <i class="c-icobox c-icobox__ico"></i>
          <input
            class="c-icobox c-icobox__inp"
            type="password"
            placeholder="Password"
            v-model="acc.password"
          />
          <label class="c-icobox c-icobox__lbl" for="">Password</label>
        </div>
      </div>
      <!-- 按鈕 -->
      <div class="l-form__btn">
        <div class="l-link">
          <p>No account ?</p>
          <a href="#" class="o-link">&nbsp;Sign up</a>
        </div>
        <button class="o-btn" @click="checking()">Login</button>
      </div>
    </section>
  </div>
</template>

<script>
import identityCard from "@/components/IdentityCard.vue";

export default {
  components: {
    identityCard,
  },
  props: ["identity", "idx"],
  data() {
    return {
      identities: ["Doctor", "Patient"],
      acc: {
        username: "",
        password: "",
      },
    };
  },
  methods: {
    checking() {
      let nameArr = this.acc.username.split("");
      let nameStr = this.acc.username;
      let pswArr = this.acc.password.split("");
      let pswStr = this.acc.password;

      if (nameArr.length < 6 || pswArr.length < 6) {
        alert("帳號或密碼至少需 6 字元");
        return;
      }

      for (let i = 0; i < pswArr.length; i++) {
        let str = pswStr.slice(i, i + 6);
        // console.log(str);
        if (nameStr.includes(str)) {
          alert("密碼不可與帳號任意 6 碼重複");
          return;
        } else {
          alert("登入成功");
          return;
        }
      }
    },
  },
};
</script>
