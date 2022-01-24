<template>
  <q-page class="flex flex-center">
    <p>
      Testing I18n Translation on Production Environments with restrictive CSP
      Header.
    </p>

    <br /><br />

    <p>
      <i>{{ $t("example") }}</i>
    </p>

    <!-- ADD CSP Header-->
    <teleport to="head" v-if="prod">
      <meta http-equiv="Content-Security-Policy" content="default-src 'self'" />
    </teleport>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "PageIndex",
  setup() {
    const prod = true; // process.env.NODE_ENV != "production";
    return { prod };
  },
});
</script>
