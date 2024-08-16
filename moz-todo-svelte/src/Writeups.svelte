<script>
    let writeups = [
      { title: "Challenge 1", content: "Write-up for Challenge 1" },
      { title: "Challenge 2", content: "Write-up for Challenge 2" },
    ];
  </script>
  
  <div class="writeups">
    <h2>Writeups</h2>
    {#each writeups as writeup}
      <div class="writeup">
        <h3>{writeup.title}</h3>
        <p>{writeup.content}</p>
      </div>
    {/each}
  </div>
  
  <style>
    .writeups {
      margin-bottom: 2rem;
    }
  
    .writeup {
      margin-bottom: 1rem;
    }
  
    h2, h3 {
      color: #00ff00;
    }
  
    p {
      color: #b0ffb0;
    }
  </style>
  