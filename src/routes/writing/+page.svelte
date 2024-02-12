<script lang="ts">
  import Seo from "$lib/components/Seo.svelte";
  import WritingList from "./WritingList.svelte";
  import writing from "./writing.yaml";
</script>

<Seo
  title="Liam Haller – Research"
  description="Published journal articles, working papers, book chapters, presentations and technical blog posts."
/>

<section class="layout-md py-12">
  <h2 class="heading2">Journal Articles</h2>
  <WritingList data={writing.articles} />
</section>

<section class="layout-md py-12">
  <h2 class="heading2">Working papers & Book chapters</h2>
  <WritingList data={writing.papers} />
</section>

<section class="layout-md py-12">
  <h2 class="heading2">Presentations</h2>
  <WritingList data={writing.presentations} />
</section>