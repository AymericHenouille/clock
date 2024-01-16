<script>
  import { linear } from 'svelte/easing';
  import { tweened } from 'svelte/motion';

  const left = tweened(0, {
		duration: 400,
		easing: linear,
	});

  setInterval(() => {
    left.update(n => (++n) % 100);
  }, 400);
</script>

<main>
  <div class="line" style="left: {$left}%"></div>
</main>

<style>
  main {
    height: 100%;
    width: 100%;
  }

  .line {
    width: 5px;
    height: 100%;
    background-color: #368974;
    position: fixed;
  }
</style>