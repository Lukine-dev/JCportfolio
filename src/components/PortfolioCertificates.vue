<template>
  <div>
    <h3 class="section-title" style="color: blueviolet;">Certificates</h3>
    <div class="row g-4">
      <div v-for="cert in certificates" :key="cert.id" class="col-md-12">
        <div class="card1">
          <div class="card-body">
            <h5 class="card-title" >{{ cert.title }}</h5>
            <p><strong>Issuer:</strong> {{ cert.issuer }}</p>
            <p><strong>Date:</strong> {{ cert.date_issued }}</p>
            <p v-if="cert.credential_id"><strong>ID:</strong> {{ cert.credential_id }}</p>
            <a v-if="cert.credential_url" :href="cert.credential_url" class="btn btn-sm btn-outline-primary" target="_blank">Verify</a>
            <p class="mt-2">{{ cert.description }}</p>
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
      certificates: []
    }
  },
  async mounted() {
    try {
      const res = await axios.get('https://nibgledxgnxbmiauwfcq.supabase.co/rest/v1/certificates', {
        headers: {
          apikey: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Im5pYmdsZWR4Z254Ym1pYXV3ZmNxIiwicm9sZSI6ImFub24iLCJpYXQiOjE3NDc2ODAzNjcsImV4cCI6MjA2MzI1NjM2N30.vbUD98QF3rBzBQREvxFGKgFW4NGzVQhm0B-VxeRyk1c',
          Authorization: 'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Im5pYmdsZWR4Z254Ym1pYXV3ZmNxIiwicm9sZSI6ImFub24iLCJpYXQiOjE3NDc2ODAzNjcsImV4cCI6MjA2MzI1NjM2N30.vbUD98QF3rBzBQREvxFGKgFW4NGzVQhm0B-VxeRyk1c'
        }
      })
      this.certificates = res.data
    } catch (error) {
      console.error('Error loading certificates:', error)
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
  background-color: transparent;
  color: #fff;
  border: none;
}

</style>
