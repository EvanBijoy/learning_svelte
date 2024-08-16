<script>
    let resources = [
      { name: "Resource 1", link: "https://example.com" },
      { name: "Resource 2", link: "https://example.com" },
    ];
  </script>
  
  <div class="resources">
    <h2>Resources</h2>
    <ul>
      {#each resources as resource}
        <li>
          <a href={resource.link} target="_blank">{resource.name}</a>
        </li>
      {/each}
    </ul>
  </div>
  
  <style>
    .resources {
      margin-bottom: 2rem;
    }
  
    h2 {
      color: #00ff00;
    }
  
    ul {
      list-style-type: none;
      padding-left: 0;
    }
  
    li {
      margin-bottom: 0.5rem;
    }
  
    a {
      color: #b0ffb0;
      text-decoration: none;
    }
  
    a:hover {
      text-decoration: underline;
    }
  </style>
  