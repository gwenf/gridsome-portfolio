<template>
  <section id="projects" class="project-section">
    <v-container>
      <v-row>
        <v-col>
          <h1>Projects</h1>
        </v-col>
      </v-row>
      <v-row class="justify-space-around mb-8 mt-4">
        <v-card
          v-for="project in projects"
          :key="project.name"
          class=""
          max-width="300"
        >
          <v-img
            class="align-end"
            height="200px"
            :src="project.image"
          />
          <v-card-title>{{ project.name }}</v-card-title>

          <v-card-text class="text--primary">
            {{ truncate(project.description) }}
          </v-card-text>

          <v-card-actions>
            <v-btn
              color="orange"
              text
              :href="project.github"
            >
              Github Repo
            </v-btn>

          </v-card-actions>
        </v-card>
      </v-row>
    </v-container>
  </section>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          name: 'Curriculum',
          github: 'https://github.com/gwenf/curriculum-app',
          description: 'This app allows users to create their own learning curriculum. They can then keep track of their progress, share it with friends, and make changes as they go along.',
          image: 'https://raw.githubusercontent.com/gwenf/curriculum-app/master/mockups/user_dashboard.png'
        },
        {
          name: 'Hour Tracking App',
          github: 'https://github.com/gwenf/vue-nwjs-hours-tracking',
          description: 'This app is to help you track your hours and generate invoices for clients as a freelancer or consultant.',
          image: 'https://raw.githubusercontent.com/gwenf/vue-nwjs-hours-tracking/master/mockups/Projects%20Page.png'
        }
      ]
    }
  },
  methods: {
    truncate(str) {
      if (str.length > 80) {
        return str.slice(0, 79) + '...'
      }
      return str
    }
  }
}
</script>

<style scoped>
.project-section {
  background-color: #FFD563;
}
.v-image {
  border-bottom: 1px solid;
}
</style>
