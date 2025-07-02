<script setup>
// Importe les fichiers Markdown depuis le dossier "articles"
const articles = import.meta.glob('/ressources/*.md', { eager: true });

const articleList = Object.entries(articles).map(([path, mod]) => {
  return {
    title: mod?.frontmatter?.title || path.split('/').pop().replace('.md', ''),
    link: path.replace('/ressources', '').replace('.md', '')
  };
});
</script>

<template>
  <div>
    <h2 class="text-2xl font-bold mb-4">📚 Articles</h2>
    <ul class="list-disc pl-6">
      <li v-for="article in articleList" :key="article.link">
        <a :href="`/ressources${article.link}`" class="text-blue-600 hover:underline">
          {{ article.title }}
        </a>
      </li>
    </ul>
  </div>
</template>