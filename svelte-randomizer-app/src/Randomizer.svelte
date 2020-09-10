<script>
  export let list;
  let chosen = 'Choose';

  const choose = (e) => {
    e.preventDefault();
    chosen = list[Math.floor(Math.random() * list.length)].item.toUpperCase();
  }
</script>
<div class="randomize-box">
  <p class="chosen">{chosen}</p>

  <button class="btn" on:click={choose}>Choose</button> 
</div>
