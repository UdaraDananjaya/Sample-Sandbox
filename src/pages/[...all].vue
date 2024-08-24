<template>
  <v-app>
    <v-container>
      <v-empty-state
        headline="Whoops, 404"
        title="Page not found"
        text="The page you were looking for does not exist"
        image="https://vuetifyjs.b-cdn.net/docs/images/logos/v.png"
      >
        <template v-slot:actions>
          <v-btn
            class="text-none"
            elevation="1"
            rounded="lg"
            size="large"
            @click="onClickAction"
          >
            {{ actionText }}
          </v-btn>
        </template>
      </v-empty-state>
    </v-container>
  </v-app>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { useRouter } from 'vue-router';

const router = useRouter();

const actionText = ref('Go Back');

function onClickAction() {
  actionText.value = 'Redirecting...';
  setTimeout(() => {
    router.push('/');
  }, 500);
}
</script>
<route lang="yaml">
  name: name-override
  meta:
    layout: blank
  </route>