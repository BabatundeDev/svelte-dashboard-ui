<script>
  import Navbar from './components/Navbar.svelte';
  import Card from './components/Card.svelte';

  let selected = "";

  let items = [
    { title: "UI Project", desc: "Responsive frontend build" },
    { title: "API Project", desc: "Fetch and display data" },
    { title: "Dashboard", desc: "Admin interface design" }
  ];

  function handleSelect(title) {
    selected = title;
  }

  let newProject = "";

  function addProject() {
    if (!newProject) return;

    items = [...items, { title: newProject, desc: "New project" }];
    newProject = "";
  }
</script>

<Navbar />

<main>
  <h1>Projects</h1>

  <!-- INPUT SECTION -->
  <div class="input-group">
    <input
      placeholder="New project"
      bind:value={newProject}
    />
    <button on:click={addProject}>Add</button>
  </div>

  {#if selected}
    <p class="selected">Selected: {selected}</p>
  {/if}

  <div class="grid">
    {#each items as item}
      <Card
        title={item.title}
        desc={item.desc}
        onSelect={() => handleSelect(item.title)}
      />
    {/each}
  </div>
</main>

<style>
  main {
    padding: 32px 24px;
    background: #0b0b0c;
    min-height: 100vh;
    color: #e5e7eb;
  }

  h1 {
    font-size: 28px;
    font-weight: 600;
    margin-bottom: 16px;
  }

  .input-group {
    margin-bottom: 20px;
  }

  input {
    padding: 8px;
    margin-right: 10px;
    border-radius: 6px;
    border: none;
  }

  button {
    padding: 8px 12px;
    border-radius: 6px;
    border: none;
    background: #4ade80;
    cursor: pointer;
  }

  .selected {
    margin-bottom: 20px;
    padding: 10px 14px;
    border-radius: 8px;
    background: rgba(74, 222, 128, 0.1);
    color: #4ade80;
    font-size: 14px;
    width: fit-content;
  }

  .grid {
    margin-top: 20px;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 20px;
  }
</style>