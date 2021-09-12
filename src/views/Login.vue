<template>
  <div>
    <p>Choose Account Type</p>
    <!-- 身分選擇 -->
    <ul class="l-identityCard">
      <li
        class="l-identityCard__item"
        v-for="(person, idx) in identities"
        :key="idx"
      >
        <IdentityCard :identity="person"></IdentityCard>
      </li>
    </ul>
    <!-- 招呼語 -->
    <div>
      <p>Hello Doctor</p>
      <p>Lorem ipsum dolor sit amet.</p>
    </div>
    <!-- 登入欄位 -->
    <div>
      <input type="email" placeholder="EMAIL" />
      <input type="text" />
    </div>
    <div>
      <button class="o-btn">Login</button>
    </div>
  </div>
</template>

<script>
import IdentityCard from "@/components/IdentityCard.vue";
export default {
  components: {
    IdentityCard,
  },
  props: ["identity"],
  data() {
    return {
      identities: [
        "Doctor",
        "Patient",
        "Doctor",
        "Doctor",
        "Doctor",
        "Doctor",
        "Doctor",
      ],
    };
  },
};
</script>
