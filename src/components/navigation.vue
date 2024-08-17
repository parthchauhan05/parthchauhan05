<script setup>
import { ref, computed } from "vue";
import jump from 'jump.js';

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
        location: '.hero'
    },
    {
        label: 'Jounery',
        icon: 'pi pi-wave-pulse',
        location: '.education'
    },
    {
        label: 'Expertises',
        icon: 'pi pi-sparkles',
        location: '.expertise'

    },
    {
        label: 'Contact',
        icon: 'pi pi-phone',
        location: '.contact'
    },
]);

const goTo = (location) => {
    jump(location, {
        duration: 500,
        offset: -80
    })
}
</script>
<template>
  <Menubar :model="items" class="parth-navigation">
    <template #start v-if="!isMobile">
      <h3>Parth Chauhan</h3>
    </template>
    <template #item="{ item, props }">
        <a v-ripple class="flex items-center" v-bind="props.action" @click="goTo(item.location)">
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
        padding: 10px 50px;
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
        .p-menubar-item:hover {
            color: var(--p-menubar-item-focus-color);
            background-color: var(--p-menubar-item-focus-background);
            border-radius: 5px;
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
    .p-menubar-item.p-focus > .p-menubar-item-content,  .p-menubar-item.p-focus > .p-menubar-item-content:hover{
        background: unset !important;
        color: unset !important;
    }
    &.p-menubar-mobile .p-menubar-root-list {
        background-color: var(--p-primary-800);
        border: none;
    }
}
</style>