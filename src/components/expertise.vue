<script setup>
import { ref } from "vue";

const expertise = ref([
  {
    name: "Vue",
    icon: "../../public/tech/vue.svg",
    level: "Advanced",
  },
  {
    name: "JavaScript",
    icon: "../../public/tech/javascript.svg",
    level: "Advanced",
  },
  {
    name: "TypeScript",
    icon: "../../public/tech/typescript.svg",
    level: "Advanced",
  },
  {
    name: "HTML",
    icon: "../../public/tech/html5.svg",
    level: "Advanced",
  },
  {
    name: "CSS",
    icon: "../../public/tech/css3.svg",
    level: "Advanced",
  },
  {
    name: "React",
    icon: "../../public/tech/react.svg",
    level: "Intermediate",
  },
  {
    name: "Pinia",
    icon: "../../public/tech/pinia.svg",
    level: "Advanced",
  },
  {
    name: "SCSS",
    icon: "../../public/tech/scss.svg",
    level: "Intermediate",
  },
  {
    name: "Shopify",
    icon: "../../public/tech/shopify.svg",
    level: "Basic",
  },
  {
    name: "Python",
    icon: "../../public/tech/python.svg",
    level: "Intermediate",
  },
  {
    name: "MongoDB",
    icon: "../../public/tech/mongodb.svg",
    level: "Intermediate",
  }
]);

const tools = ref([
  {
    name: "Git",
    icon: "../../public/tech/git.svg",
    level: "Advanced",
  },
  {
    name: "GitHub",
    icon: "../../public/tech/github.svg",
    level: "Advanced",
  },
  {
    name: "VS Code",
    icon: "../../public/tech/vscode.svg",
    level: "Advanced",
  },
  {
    name: "Jira",
    icon: "../../public/tech/jira.svg",
    level: "Intermediate",
  },
  {
    name: "Slack",
    icon: "../../public/tech/slack.svg",
    level: "Intermediate",
  },
  {
    name: "Office 365",
    icon: "../../public/tech/office365.svg",
    level: "Intermediate",
  },
])
</script>

<template>
  <section class="expertise">
    <h3>Expertise</h3>
    <i class="pi pi-ellipsis-h" style="font-size: 2rem;color: var(--p-primary-color);"></i>
    <div class="expertise-list">
      <div v-for="item in expertise" :key="item.name" class="expertise-list-item">
        <img :src="item.icon" :alt="item.name" />
        <p>{{ item.name }}</p>
        <Tag :severity="item.level === 'Basic' ? 'info' : item.level === 'Intermediate' ? 'secondary' : 'success'">{{ item.level }}</Tag>
      </div>
      <Divider />
    </div>
    <h3>Tools</h3>
    <i class="pi pi-ellipsis-h" style="font-size: 2rem;color: var(--p-primary-color);"></i>
    <div class="expertise-list">
      <div v-for="item in tools" :key="item.name" class="expertise-list-item">
        <img :src="item.icon" :alt="item.name" />
        <p>{{ item.name }}</p>
        <Tag :severity="item.level === 'Basic' ? 'info' : item.level === 'Intermediate' ? 'secondary' : 'success'">{{ item.level }}</Tag>
      </div>
    </div>
  </section>
</template>

<style lang="scss">
  .expertise {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
    text-align: center;
    h3 {
      font-size: 2.25rem;
      font-weight: 700;
      line-height: 2.5rem;
      margin: 0.25rem;
      color: var(--p-primary-color);
    }
    &-list {
      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: center;
      flex-wrap: wrap;
      gap: 6rem;
      margin: 2rem 0;
      img {
        width: 6rem;
        height: 6rem;
      }
      &-item {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        p {
          font-size: 1.25rem;
          font-weight: 500;
          line-height: 2rem;
          margin: 0.5rem;
          color: var(--p-primary-color);
        }
      }
    }
  }
</style>