<script>

type Project = {
    title: string;
    date: string;
  };

  export let data: Project;
    export let post;
  </script>
  
  <article>
    <h1>{data.title}</h1>
    <p>{data.date}</p>
    <div>{@html data.markdown}</div>
  </article>
  