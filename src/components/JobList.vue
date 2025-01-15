<template>
  <div>
    <h1>Available Jobs</h1>
    <ul>
      <li v-for="job in jobs" :key="job.id">{{ job.title }}</li>
    </ul>
  </div>
</template>

<script>
import api from "../service/api";

export default {
  data() {
    return {
      jobs: [],
    };
  },
  async created() {
    const response = await api.get("/jobs");
    this.jobs = response.data;
  },
};
</script>
