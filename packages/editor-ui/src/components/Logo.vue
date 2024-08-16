<template>
	<img :src="logoPath" :class="$style.img" alt="n8n.io" />
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { mapStores } from 'pinia';
import { useRootStore } from '@/stores/root.store';
import { useUIStore } from '@/stores/ui.store';
import Logo from '@/assets/n8n-logo.png';

export default defineComponent({
	computed: {
		...mapStores(useRootStore, useUIStore),
		basePath(): string {
			return this.rootStore.baseUrl;
		},
		logoPath(): string {
			return Logo;
		},
	},
});
</script>

<style lang="scss" module>
.img {
	height: 32px;
}
</style>
