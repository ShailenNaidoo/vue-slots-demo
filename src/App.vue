<template>
  <v-container text-md-center text-sm-center text-xs-center>
    <named-slots>
      <p slot="header" class="display-2">Lorem ipsum dolor sit amet consectetur adipisicing elit. Molestiae suscipit facilis repudiandae quis quidem, numquam amet. Dolorem, molestiae dolor. Nisi reiciendis maiores fugit consequatur veritatis commodi nulla! Labore, voluptatem enim?</p>
      <p class="display-2">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Corrupti dolore animi fuga placeat, aspernatur natus iste ullam totam architecto laborum repudiandae, blanditiis sint eius beatae tempore atque repellat nesciunt rem.</p>
      <p slot="footer" class="display-2">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Corrupti dolore animi fuga placeat, aspernatur natus iste ullam totam architecto laborum repudiandae, blanditiis sint eius beatae tempore atque repellat nesciunt rem.</p>
    </named-slots>
  </v-container>
</template>

<script>
import BasicUsage from "./components/BasicUsage.vue";
import NamedSlots from "./components/NamedSlots.vue";

export default {
  components: {
    BasicUsage,
    NamedSlots
  }
}
</script>