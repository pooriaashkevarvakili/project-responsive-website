<template>
  <div class="q-pa-md q-gutter-sm">
    <q-btn size=".9em" icon="fa-solid fa-user-plus" color="primary" @click="alert = true">
      <span class="q-mr-sm">
        {{ $t('AddApplicant') }}
      </span>
    </q-btn>
    <q-dialog maximized v-model="alert">
      <div>
        <q-card style="max-width: 800px; width: 1000px; height: 800px">
          <q-btn icon="close" class="q-mr-sm q-mt-sm" v-close-popup flat dense />
          <TabApplicant />
        </q-card>
      </div>
    </q-dialog>
  </div>
</template>
<script setup>
import { ref, defineAsyncComponent } from 'vue'
const TabApplicant = defineAsyncComponent(() => import("./TabApplicant.vue"))
const alert = ref(false)
const tab = ref('mails')
</script>
