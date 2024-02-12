<script lang="ts">
  import { ArrowUpRight } from "lucide-svelte";

  import Seo from "$lib/components/Seo.svelte";

  const featuredProjects = [
    {
      name: "A not-so 'natural' decision",
      href: "https://doi.org/10.1080/1369183X.2023.2268844",
      desc: "A new qualitative framework for naturalization decisions",
    },
    {
      name: "surveyexplorer - R package",
      href: "/projects#surveyexplorer",
      desc: "Quickly Explore Complex Survey Data",
    },
    {
      name: "R package for complex survey data",
      href: "/projects#percival",
      desc: "reactive notebooks for exploratory data analysis",
    },
    {
      name: "Rustpad",
      href: "/projects#rustpad",
      desc: "self-hosted collaborative text editor",
      aside: "2M+ downloads",
    },
  ];
</script>

<Seo
  title="Liam Haller"
  description="Researcher, software engieer, and designer. Making meaningful systems and interfaces for people."
/>

<!-- <p
  class="layout-md text-black text-xl leading-tight font-light mb-16"
  id="eric-is"
>
  <span class="g">is a</span> software writer<span class="g">,</span><br />
  researcher<span class="g">, and</span><br />
  designer<span class="g">.</span>
</p>
 -->

<br>
<br>
<br>

<div class="layout-md text-lg space-y-14">
  <div class="md:flex">
    <div class="md:shrink-0">
      <img class="object-scale-down h-70 w-60 rounded-xl" src="/assets/images/liam_dezim.jpg" alt="Modern building architecture">
    </div>
    <div class="md:p-10">
      <div class="uppercase tracking-wide text-sm text-black-500 font-semibold">Hello!</div>
      <br>
      <p class="space-y-5">My name is Liam and I am a migration researcher at the 
        <a class="link" href="https://www.dezim-institut.de/en/institute/about-dezim/" target="_blank" >
          DeZIM institute</a> in Berlin. My aim is to better understand migration decisions and trajectories 
          using quantitative methods and through the study of complex systems.  

      </p>
    </div>
  </div>
</div>

<br>

<div class="layout-md text-lg space-y-14">

  <div class="space-y-5">
    <p>
      My current research includes the the development of large-scale, agent-based simulations,
      the application of Bayesian methods, and the use of Markov chains to model forced migrant trajectories. 

    </p>

    <p>
      Previously, I was awareded a Fulbright research grant to ...  Before that, I worked as a software engineer at McMaster-Carr and conducted research in 
      combinatorics. 
    </p>

  </div>


  <div class="leading-snug space-y-4">
    <p class="pb-2">Selected research & projects:</p>

    {#each featuredProjects as project}
      <a class="project-pair" href={project.href}>
        <div class="text-black font-medium">
          {project.name}
          <ArrowUpRight size={18} class="inline text-neutral-400" />
        </div>
        <div>
          <p>{project.desc}</p>
          {#if project.aside}
            <aside>{project.aside}</aside>
          {/if}
        </div>
      </a>
    {/each}
  </div> 



  <div class="space-y-5">

    <p>
       I gratudated from Northwestern University, where I studied in mathemtatics and several 
       foreign langauges. 
       
       To varying degrees of fluency, I can speak Arabic (shami/fausa), German, French,
       Hebrew, and Portuguese (br). I also took some masters-level coursework in finaincal economics thorugh 
       the Kellogg certificate program. 
    </p>

    <p>
      Other interests: leatherworking, baking bagels, triathalons
    </p>

  </div>




</div>

<style lang="postcss">
  .g {
    @apply text-neutral-400;
  }

  em {
    @apply font-serif text-[110%] leading-[100%];
  }

  .project-pair {
    @apply grid sm:grid-cols-[1fr,2fr] gap-y-1 -mx-3 px-3 py-2 hover:bg-neutral-100 transition-colors;
  }

  aside {
    @apply mt-0.5 text-base text-neutral-500;
  }

  /* Correction for vertical navigation links on mobile. */
  @media (max-width: 420px) {
    #eric-is {
      @apply -mt-10;
    }
  }
</style>
