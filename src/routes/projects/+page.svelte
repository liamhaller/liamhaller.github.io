<script lang="ts">
  import { page } from "$app/stores";
  import { onMount } from "svelte";
  import Seo from "$lib/components/Seo.svelte";
  import Project from "./Project.svelte";

  const projectFiles = import.meta.glob("../../projects/*.md", {
    eager: true,
  }) as Record<string, {default: any}>;

  const imageFiles = import.meta.glob("../../projects/*.{png,jpg,svg}", {
    eager: true,
  }) as Record<string, {default: string}>;

  const projects = Object.entries(projectFiles).map(([path, module]) => {
    const name = path.match(/\.\.\/projects\/(.*)\.md$/)?.[1];
    const imageKey = `../../projects/${name}.png`; // Assumes a .png extension; adjust if needed.
    return {
      content: module.default,
      image: imageFiles[imageKey]?.default,
      name: name,
    };
  });

</script>

<Seo
  title="Liam Haller – Projects"
  description="Open-source software projects in systems, web development, computer graphics, music, programming languages, machine learning, and more."
/>


<!-- Page Title -->
<h1 class="text-3xl font-bold text-center my-8">Projects</h1>


<!-- <section class="layout-md py-12">
  <h2 class="heading2">Open Source</h2>

  <p class="text-lg mb-4">
    interested in building tools... to further research.. academic writing to document make resarch 
    more aceessible and transparent
  </p>

  <p class="text-lg mb-4">
    political risk financial economcis...
  </p>

</section>  -->

<!-- Projects List -->
<div class="layout-md py-12">
  {#each projects as project}
    <div>
      <h2 class="text-2xl font-semibold">{project.name}</h2>
      <Project data={project.content} images={imageFiles} />
    </div>
  {/each}
</div>



