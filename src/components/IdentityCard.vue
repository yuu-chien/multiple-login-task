<template>
  <!-- <div class="c-identityCard is-check">
    <div class="c-identityCard__kv">
      <img :src="require(`@/assets/image/${identity}_3x.svg`)" />
    </div>
    <div class="c-identityCard__tit">{{ identity }}</div>
  </div> -->
  <div class="c-identityCard">
    <input
      class="c-identityCard__inp"
      type="radio"
      name="identity_type"
      :id="'identity_' + idx"
    />
    <label class="c-identityCard__lbl" :for="'identity_' + idx">
      <div class="c-identityCard__kv">
        <img :src="require(`@/assets/image/${identity}_3x.svg`)" />
      </div>
      <div class="c-identityCard__tit">{{ identity }}</div>
    </label>
  </div>
</template>

<script>
export default {
  props: ["identity", "idx"],
  data() {
    return {};
  },
};
</script>
