<script setup>
import { ref } from "vue";

const expertise = ref([
  {
    name: "Vue",
    icon: "../../tech/vue.svg",
    level: "Advanced",
  },
  {
    name: "JavaScript",
    icon: "../../tech/javascript.svg",
    level: "Advanced",
  },
  {
    name: "TypeScript",
    icon: "../../tech/typescript.svg",
    level: "Advanced",
  },
  {
    name: "React",
    icon: "../../tech/react.svg",
    level: "Intermediate",
  },
  {
    name: "Pinia",
    icon: "../../tech/pinia.svg",
    level: "Advanced",
  },
  {
    name: "Element Plus",
    icon: "../../tech/element-plus.svg",
    level: "Advanced",
  },
  {
    name: "HTML",
    icon: "../../tech/html5.svg",
    level: "Advanced",
  },
  {
    name: "CSS",
    icon: "../../tech/css3.svg",
    level: "Advanced",
  },
  {
    name: "SCSS",
    icon: "../../tech/scss.svg",
    level: "Intermediate",
  },
  {
    name: "Bootstrap",
    icon: "../../tech/bootstrap.svg",
    level: "Intermediate",
  },
  {
    name: "Shopify",
    icon: "../../tech/shopify.svg",
    level: "Basic",
  },
  {
    name: "Python",
    icon: "../../tech/python.svg",
    level: "Intermediate",
  },
  {
    name: "Django",
    icon: "../../tech/django.svg",
    level: "Basic",
  },
  {
    name: "Ruby",
    icon: "../../tech/ruby.svg",
    level: "Intermediate",
  },
  {
    name: "Ruby on Rails",
    icon: "../../tech/rails.svg",
    level: "Intermediate",
  },
  {
    name: "SQL",
    icon: "../../tech/sql.svg",
    level: "Intermediate",
  },
  {
    name: "MongoDB",
    icon: "../../tech/mongodb.svg",
    level: "Intermediate",
  }
]);

const tools = ref([
  {
    name: "Git",
    icon: "../../tech/git.svg",
    level: "Advanced",
  },
  {
    name: "GitHub",
    icon: "../../tech/github.svg",
    level: "Advanced",
  },
  {
    name: "VS Code",
    icon: "../../tech/vscode.svg",
    level: "Advanced",
  },
  {
    name: "Jira",
    icon: "../../tech/jira.svg",
    level: "Intermediate",
  },
  {
    name: "Confluence",
    icon: "../../tech/confluence.svg",
    level: "Intermediate",
  },
  {
    name: "Slack",
    icon: "../../tech/slack.svg",
    level: "Intermediate",
  },
  {
    name: "Office 365",
    icon: "../../tech/office365.svg",
    level: "Intermediate",
  },
  {
    name: "Figma",
    icon: "../../tech/figma.svg",
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
    padding: 0 30px;
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
      gap: 5rem;
      margin: 2rem 0;
      @media screen and (max-width: 960px) {
        gap: 2rem;
        
      }
      img {
        width: 3rem;
        height: 3rem;
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