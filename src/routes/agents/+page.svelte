<script lang="ts">
  import Seo from "$lib/components/Seo.svelte";
  import AgentsList from "./AgentsList.svelte";
  import agents from "./agents.yaml";
</script>

<Seo
  title="Liam Haller – Research"
  description="Published journal articles, working papers, book chapters, presentations and technical blog posts."
/>

<section class="layout-md py-12">
  <h2 class="heading2">Journal Articles</h2>
  <AgentsList data={agents.articles} />
</section>
