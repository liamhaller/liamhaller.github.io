<script context="module">
    import fs from 'fs';
    import path from 'path';
    import grayMatter from 'gray-matter';
  
    export async function load({ params }) {
      const posts = fs.readdirSync('src/posts')
        .filter(file => path.extname(file) === '.md')
        .map(file => {
          const content = fs.readFileSync(`src/posts/${file}`, 'utf-8');
          const { data, content: markdown } = grayMatter(content);
          return {
            title: data.title,
            date: data.date,
            markdown,
            slug: file.slice(0, -3)
          };
      });
  
      return {
        props: {
          posts
        }
      };
    }
  </script>
  
  <script>
    export let posts;
  </script>
  
  <article>
    {#each posts as post}
      <h1>{post.title}</h1>
      <p>{post.date}</p>
      <div>{@html post.markdown}</div>
    {/each}
  </article>
  