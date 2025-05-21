<template>
  <div>
    <h3 class="section-title" style="color: blueviolet;">Projects</h3>
    <div class="row g-4">
      <div v-for="p in projects" :key="p.id" class="col-md-12">
        <div class="card1">
          <img v-if="p.image_url" :src="p.image_url" class="card-img-top" :alt="p.title" />
          <div class="card-body">
            <h5 class="card-title">{{ p.title }}</h5>
            <p class="card-text">{{ p.description }}</p>
            <p class="card-text"> <strong class="me-2">Role:</strong>{{ p.role }}</p>
            <p class="card-text">{{ p.detailed_description }}</p>
            <p><strong>Tech:</strong> {{ p.technologies }}</p>
            <a v-if="p.project_url" :href="p.project_url" target="_blank" class="btn btn-sm btn-primary mx-2 px-3">Live</a>
            <a v-if="p.github_url" :href="p.github_url" target="_blank" class="btn btn-sm btn-secondary mx-2">GitHub</a>
            <small class=" d-block mt-2">Completed: {{ p.date_completed }}</small>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      projects: []
    }
  },
  async mounted() {
    try {
      const res = await axios.get('https://nibgledxgnxbmiauwfcq.supabase.co/rest/v1/projects', {
        headers: {
          apikey: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Im5pYmdsZWR4Z254Ym1pYXV3ZmNxIiwicm9sZSI6ImFub24iLCJpYXQiOjE3NDc2ODAzNjcsImV4cCI6MjA2MzI1NjM2N30.vbUD98QF3rBzBQREvxFGKgFW4NGzVQhm0B-VxeRyk1c',
          Authorization: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Im5pYmdsZWR4Z254Ym1pYXV3ZmNxIiwicm9sZSI6ImFub24iLCJpYXQiOjE3NDc2ODAzNjcsImV4cCI6MjA2MzI1NjM2N30.vbUD98QF3rBzBQREvxFGKgFW4NGzVQhm0B-VxeRyk1c'
        }
      })
      this.projects = res.data
    } catch (error) {
      console.error('Error loading projects:', error)
    }
  }
}
</script>

<style scoped>
.section-title {
  border-bottom: 2px solid #ddd;
  margin-top: 2rem;
  padding-bottom: 0.5rem;
}
.card1 {
  min-width: 100%;
  background-color: transparent ;
  color: #fff;
  border: none;
}
</style>
