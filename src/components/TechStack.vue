<template>
  <section id="technologies" class="mb-5">
    <h2 class="section-title" style="color:blueviolet">Technologies</h2>
    <div class="d-flex flex-wrap gap-2">
      <span class="badge tech-badge">Laravel</span>
      <span class="badge tech-badge">Vue Js</span>
      <span class="badge tech-badge">Express Js</span>
      <span class="badge tech-badge">WordPress</span>
      <span class="badge tech-badge">React.js</span>
      <span class="badge tech-badge">Node.js</span>
      <span class="badge tech-badge">PostgreSQL</span>
      <span class="badge tech-badge">Supabase</span>
      <span class="badge tech-badge">MongoDB</span>
      <span class="badge tech-badge">GraphQL</span>
    </div>
  </section>
</template>

<script>
export default {
  name: "TechStackSection"
};
</script>

<style scoped>
.section-title {
  border-bottom: 2px solid #ddd;
  margin-bottom: 1rem;
  padding-bottom: 0.5rem;
}
span{
  background-color: blueviolet;
  border-radius: 32px;
  padding-left: 1rem;
  padding-right: 1rem;
}
</style>