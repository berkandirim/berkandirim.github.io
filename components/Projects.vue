<template>
  <section class="projects section">
    <h2 class="section-title">Some Projects</h2>
    <p>Here are a few personal and commercial projects.</p>
    <ul class="project-list">
      <li v-for="project in projects" :key="slugify(project.name)">
        <h3><a class="project-name link" :href="project.link" target="_blank" rel="noreferrer">{{project.name}}</a></h3>
        <p v-html="project.description"></p>
      </li>
    </ul>
  </section>
</template>

<script>
  export default {
    methods: {
      slugify (str) {
        return str.toLowerCase().split(' ').join('-');
      }
    },
    data () {
      return {
        projects: [
          {
            name: 'Publing Display',
            link: 'https://www.publing.co/',
            description: 'Collect all content related to your business and display it on many different screens. I have developed a UI and different themes for this project.'
          },
          {
            name: 'Publing Social Grader',
            link: 'https://grader.publing.co/',
            description: 'Grade your social media, get recommendations on how to improve your online presence. The UI is developed by me.'
          },
          {
            name: 'jQuery Listswap',
            link: 'http://berkandirim.github.io/jquery-listswap',
            description: 'A jquery plugin that lets you swap options between select lists.'
          },
          {
            name: 'Luxbar Hide',
            link: 'https://github.com/berkandirim/luxbar-hide',
            description: 'A luxbar plugin to hide luxbar while scrolling down.'
          },
          {
            name: 'Jekyll UXRocket',
            link: 'https://github.com/berkandirim/jekyll-uxrocket',
            description: 'A Jekyll boilerplate using <a class="link" href="https://github.com/uxrocket">UX Rocket</a> elements, <a class="link" href="https://github.com/bcinarli/melange">Melange</a> and <a class="link" href="https://github.com/bcinarli/caffeine">Caffeine</a>.'
          }
        ]
      }
    }
  }
</script>

<style lang="scss">
  @import "../assets/scss/vars";

  .project-list {
    list-style: none;
    p {
      margin-bottom: 1rem;
    }
  }

  .project-name {
    margin-left: -4px;
  }
</style>
