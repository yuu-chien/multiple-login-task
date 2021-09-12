<template>
  <div class="c-identityCard is-check">
    <div class="c-identityCard__kv">
      <img :src="require(`@/assets/image/${identity}_3x.svg`)" />
    </div>
    <div class="c-identityCard__tit">{{ identity }}</div>
  </div>
</template>

<script>
export default {
  props: ["identity"],
  data() {
    return {};
  },
};
</script>
