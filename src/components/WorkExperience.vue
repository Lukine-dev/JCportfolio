
<template>
  <section id="experience" class="py-5">
    <h2 class="section-title" style="color:blueviolet">Experience</h2>
    <div v-for="work in workExperiences" :key="work.id" class="mb-4">
      <div class="d-flex align-items-center gap-3">
        <img v-if="work.logo_url" :src="work.logo_url" alt="Company Logo" class="rounded-circle" width="50" height="50">
        <h5 class="mb-0">{{ work.position }} – {{ work.company_name }}</h5>
      </div>
      <p><em>{{ formatDate(work.start_date) }} – {{ work.currently_working ? 'Present' : formatDate(work.end_date) }}</em></p>
      <p>{{ work.description }}</p>
      <div v-if="work.skills">
        <strong>Skills:</strong>
        <span v-for="skill in work.skills.split(',')" :key="skill" class="badge mx-1">{{ skill.trim() }}</span>
      </div>
    </div>
  </section>
</template>

<script>
import axios from 'axios';
export default {
  name: "WorkExperienceSection",
  data() {
    return {
      workExperiences: []
    };
  },
  mounted() {
    axios.get('https://nibgledxgnxbmiauwfcq.supabase.co/rest/v1/work_experiences', {
      headers: {
        apikey: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Im5pYmdsZWR4Z254Ym1pYXV3ZmNxIiwicm9sZSI6ImFub24iLCJpYXQiOjE3NDc2ODAzNjcsImV4cCI6MjA2MzI1NjM2N30.vbUD98QF3rBzBQREvxFGKgFW4NGzVQhm0B-VxeRyk1c',
        Authorization: 'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Im5pYmdsZWR4Z254Ym1pYXV3ZmNxIiwicm9sZSI6ImFub24iLCJpYXQiOjE3NDc2ODAzNjcsImV4cCI6MjA2MzI1NjM2N30.vbUD98QF3rBzBQREvxFGKgFW4NGzVQhm0B-VxeRyk1c'
      }
    })
    .then(response => {
      this.workExperiences = response.data;
    })
    .catch(error => {
      console.error('Failed to fetch work experiences:', error);
    });
  },
  methods: {
    formatDate(date) {
      if (!date) return '';
      return new Date(date).toLocaleDateString('en-US', { year: 'numeric', month: 'short' });
    }
  }
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