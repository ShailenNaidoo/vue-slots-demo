<template>
  <v-container text-md-center text-sm-center text-xs-center justify-center>
    <v-progress-circular v-if="loading" indeterminate></v-progress-circular>
    <linxios url="https://dev.to" @loading="e => loading = e">
      <v-card slot-scope="{ state, actions }" width="300px" >
        <div v-if="state.loaded">
          <v-card-title>{{ state.meta.og.title }}</v-card-title>
          <v-progress-circular v-if="state.imageLoading" indeterminate></v-progress-circular>
          <v-img v-show="state.imageLoaded" v-bind:src="state.meta.og.image" @load="actions.setImageLoaded()"></v-img>
          <v-card-text>{{ state.meta.og.description }}</v-card-text>
          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn small flat round v-bind:href="state.meta.og.url">check it out</v-btn>
          </v-card-actions>
        </div>
      </v-card>
    </linxios>
  </v-container>
</template>

<script>
import BasicUsage from "./components/BasicUsage.vue";
import NamedSlot from "./components/NamedSlot.vue";
import NamedSlotHeader from "./components/NamedSlotHeader.vue";
import NamedSlotMain from "./components/NamedSlotMain.vue";
import NamedSlotFooter from "./components/NamedSlotFooter.vue";
import ScopedSlot from "./components/ScopedSlot.vue";
import { Linxios } from "@webdataorg/linxios-vue";

export default {
  components: {
    BasicUsage,
    NamedSlot,
    NamedSlotHeader,
    NamedSlotMain,
    NamedSlotFooter,
    ScopedSlot,
    Linxios
  },
  data() {
    return {
      loading: false
    }
  }
}
</script>