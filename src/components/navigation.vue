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
        <Button outlined rounded as="a" href="https://wa.me/+16135012020" target="_blank">
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
        background-color: var(--p-primary-800);
        border-radius: 0;
        color: white;
        position: sticky;
        position: -webkit-sticky; 
        z-index: 10000; 
        top: 0;
        a, .p-button {
            color: white;
            text-decoration: none;
            &:hover {
                color: var(--p-highlight-color);
            }
        }
        &.p-focus {
            color: var(--p-highlight-color);
        }
        h3 {
            font-size: 2.25rem;
            font-weight: 600;
            line-height: 2.5rem;
            margin-bottom: 1rem ; 
            margin-top: 0.5rem;
            // color: var(--p-highlight-color);
        }
    }
    
    .p-menubar-end {
        margin-left: 0;
    }
}
</style>