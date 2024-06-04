<template>
  <div v-if="loading">
    <p>Loading repository details...</p>
  </div>
  <div v-else>
    <h1>{{ repoDetails.name }}</h1>
    <p>{{ repoDetails.description }}</p>
    <h2>Branches</h2>
    <ul v-if="branches.length">
      <li v-for="branch in branches" :key="branch.name">
        {{ branch.name }}
      </li>
    </ul>
    <p v-else>No branches found.</p>
    <h2>Deployments (Example)</h2>
    <ul v-if="deploys.length">
      <li v-for="deployment in deploys" :key="deployment.id">
        {{ deployment.name }} ({{ deployment.environment }})
      </li>
    </ul>
    <p v-else>No deployments found (replace with your API endpoint).</p>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      repoDetails: {},
      branches: [],
      loading: true,
      deploys: [],
    };
  },
  methods: {
    async fetchData() {
      this.loading = true;
      try {
        const response = await axios.get(`https://api.github.com/repos/Vicky041/${this.$route.params.repo}`);
        this.repoDetails = response.data;

        // Fetch branches (replace with your API endpoint if different)
        const branchesResponse = await axios.get(`https://api.github.com/repos/Vicky041/${this.$route.params.id}/branches`);
        this.branches = branchesResponse.data;

        // Fetch deployments (replace with your API endpoint)
        // This is an example, replace with your actual deployment data endpoint
        const deploymentsResponse = await axios.get('https://api.github.com/repos/Vicky041/${this.$route.params.id}/deployments');
        this.deploys = deploymentsResponse.data;
      } finally {
        this.loading = false; // Ensure loading state is reset even on errors
      }
    },
  },
  created() {
    this.fetchData(); // Fetch data on component creation
  },
};
</script>