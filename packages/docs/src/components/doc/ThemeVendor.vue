<template>
  <v-row v-if="vendor">
    <v-col
      v-for="product in vendor.products"
      :key="product.title"
      cols="12"
      sm="6"
    >
      <ThemeCard :product="product" />
    </v-col>

    <v-col class="text-center mb-8" cols="12">
      <app-btn
        :href="vendor.moreUrl"
        append-icon="mdi-open-in-new"
        color="primary"
        size="large"
        target="_blank"
        rel="noopener noreferrer"
        variant="outlined"
      >
        {{ t('see-more-themes-from', { vendor: vendor.name }) }}
      </app-btn>
    </v-col>
  </v-row>
</template>

<script setup>
  // Components
  import ThemeCard from './ThemeCard.vue'

  // Composables
  import { useI18n } from 'vue-i18n'

  // Utilities
  import { computed } from 'vue'

  // Stores
  import { useShopifyStore } from '@/store/shopify'

  const { t } = useI18n()
  const store = useShopifyStore()

  const props = defineProps({
    name: {
      type: String,
      required: true,
    },
  })

  const vendor = computed(() => store.byVendor[props.name])
</script>
