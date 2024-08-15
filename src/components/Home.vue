<script setup>
import { ref } from "vue";

const items = ref([
    {
        label: 'Home',
        icon: 'pi pi-home'
    },
    {
        label: 'Education',
        icon: 'pi pi-graduation-cap'
    },
    {
        label: 'Work Experience',
        icon: 'pi pi-desktop'
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
    <template #start>
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
    }
    
    .p-menubar-end {
        margin-left: 0;
    }
}
</style>