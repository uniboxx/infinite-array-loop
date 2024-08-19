<script lang="ts">
  import Carousel from './Layouts/Carousel.svelte';
  import Header from './Layouts/Header.svelte';
  import Backdrop from './lib/Backdrop.svelte';
</script>

<Backdrop />
<Header />
<Carousel />

<style lang="scss">
  @use './styles/vars';
</style>
