<script setup>
import { ref, computed } from "vue";

const isMobile = computed(() => window.innerWidth < 961);
const items = ref([
    {
        label: 'Parth Chauhan',
        visible: isMobile,
        disable: true
    },
    {
        label: 'Home',
        icon: 'pi pi-home',
    },
    {
        label: 'Jounery',
        icon: 'pi pi-wave-pulse'
    },
    {
        label: 'Expertises',
        icon: 'pi pi-sparkles'
    },
    {
        label: 'Contact',
        icon: 'pi pi-phone'
    },
]);
</script>
<template>
  <Menubar :model="items" class="parth-navigation">
    <template #start v-if="!isMobile">
      <h3>Parth Chauhan</h3>
    </template>
    <template #item="{ item, props }">
        <a v-ripple class="flex items-center" v-bind="props.action">
            <span :class="item.icon" />
            <span class="ml-2">{{ item.label.toUpperCase() }}</span>
        </a>
    </template>
    <template #end>
        <Button outlined rounded>
            <i class="pi pi-whatsapp"></i>
            <span>Let's talk</span>
        </Button>
    </template>
  </Menubar>
</template>
<style lang="scss">
.parth-navigation {
    justify-content: space-between;
    &.p-menubar {
        padding: 0 50px;
        border: none;
        border-bottom: 1px solid #e5e5e5;
        position: sticky;
        position: -webkit-sticky; // Needed for Safari browsers.
        z-index: 10000; // This prevents elements to be seen through the toolbar.
        top: 0;
    }
    
    .p-menubar-end {
        margin-left: 0;
    }
}
</style>