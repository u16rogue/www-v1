<script lang="ts">
  import type { PageData } from "./$types";
  import "$lib/styles.css";
  export let data: PageData;
</script>

<div class="main">
  <div class="header">
    <div class="header-content">
      <p class="header-title">{data.metadata.title}</p>
      <p class="header-description">{data.metadata.description}</p>
      {#if data.metadata.tags}
        <div class="article-tags">
          {#each data.metadata.tags as tag}
            <div class="article-tag">{tag}</div>
          {/each}
        </div>
      {/if}
    </div>
  </div>

  <div class="content">
    {@html data.content.code}
  </div>
</div>

<style>

  :root {
    --article-pad: 8px;  
  }

  /*------------------------------------------------------------*/

  .content { padding: 0 24px; }

  .content :global(img) {
    border-style: dashed;
    border-width: 2px;
    border-color: #826a6b;
  }

  .content :global(p) {
    margin: 0;
  }

  .content :global(a) {
    color: #5bf8ff;
    text-decoration: underline dotted;
  }

  .content :global(code) {
    background-color: #2d293b;
    width: fit-content;
    padding: 1px;
    margin: 1px;
    border-color: #826a6b;
  }

  .content :global(pre:has(code) > code) {
    background-color: #00000000;
  }

  .content :global(pre:has(code)) {
    background-color: #2d293b;
    padding: 8px;
    width: fit-content;
    border-left-style: dotted;
    border-width: 4px;
    border-color: #826a6b;
  }

  .content :global(blockquote) {
    background-color: #2d293b;
    padding: 8px;
    text-align: center;
    border-left-style: dotted;
    font-style: italic;
    width: fit-content;
    border-color: #826a6b;
  }

  .content :global(table) {
    border-style: dashed;
    border-width: 1px;
    border-color: #826a6b;
  }

  .content :global(thead) {
    font-weight: bolder;
    font-size: 1.1rem;
    background-color: #2d293b;
  }

  .content :global(tbody > tr:nth-of-type(even)) {
    background-color: #363648;
  }

  .content :global(tbody > tr:nth-of-type(odd)) {
    background-color: #3b3b5b;
  }

  .content :global(th) {
    padding: 6px;
  }

  .content :global(td) {
    padding: 4px;
  }

  /*------------------------------------------------------------*/

  .article-tags {
    margin-top: var(--article-pad);
  }

  .header-content {
  }

  .header-description {
    
  }

  .header-title {
    font-weight: bolder;
    font-size: 2rem;
  }

  .header-content > p {
    margin: 0;
  }

  .header {
    background-color: #2d293b;
    padding: var(--article-pad);
    border-left-style: solid;
    border-left-color: #826a6b;
    border-left-width: 6px;
  }

  .main {
    padding: 12px;
    color: #fff;
  }
</style>
