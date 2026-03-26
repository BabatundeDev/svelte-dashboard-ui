<script>
  export let title;
  export let desc;
  export let onSelect;
</script>

<div class="card">
  <h3>{title}</h3>
  <p>{desc}</p>
  <button on:click={onSelect}>View</button>
</div>

<style>
  .card {
  padding: 18px;
  border-radius: 14px;
  background: linear-gradient(145deg, #1a1a1a, #111);
  color: #e5e7eb;
  transition: all 0.25s ease;
  border: 1px solid rgba(255,255,255,0.05);
}

.card:hover {
  transform: translateY(-6px) scale(1.01);
  box-shadow: 0 10px 30px rgba(0,0,0,0.4);
}

h3 {
  font-size: 16px;
  margin-bottom: 6px;
}

p {
  font-size: 13px;
  color: #9ca3af;
}

button {
  margin-top: 12px;
  padding: 6px 12px;
  border-radius: 6px;
  border: none;
  background: #4ade80;
  color: #022c22;
  font-size: 13px;
  cursor: pointer;
  transition: 0.2s;
}

button:hover {
  background: #22c55e;
}
</style>