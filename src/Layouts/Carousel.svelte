<script>
  const imageUrls = [
    'https://plus.unsplash.com/premium_photo-1661815009844-0533d0d98d45?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8OXx8Z2lyYXNvbGV8ZW58MHx8MHx8fDA%3D',
    'https://images.unsplash.com/photo-1552160793-cbaf3ebcba72?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTF8fGdpcmFzb2xlfGVufDB8fDB8fHww',
    'https://images.unsplash.com/photo-1599270613570-a620f2e59f75?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTJ8fGdpcmFzb2xlfGVufDB8fDB8fHww',
  ];
  const arrayLength = imageUrls.length;

  let arrayIdx = $state(0);

  function loopArray(value) {
    arrayIdx = (arrayLength + ((arrayIdx + value) % arrayLength)) % arrayLength;
    console.log(arrayIdx);
  }
</script>

<div class="carousel">
  <button id="prev" onclick={() => loopArray(-1)}>❮</button>
  {#each imageUrls as url, idx (url)}
    <img
      src={url}
      class={`banner ${arrayIdx === idx ? 'active' : ''}`}
      alt={`banner ${idx + 1}`} />
  {/each}

  <button id="next" onclick={() => loopArray(1)}>❯</button>
</div>

<style lang="scss">
  @use '../styles/vars';

  .carousel {
    width: 60svw;
    height: 40svw;
    // height: 54rem;
    margin: 15rem auto;
    position: relative;

    & > button {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      align-self: center;
      padding: 1rem 3rem;
      margin: 0 2rem;
      border-radius: 10px;
      font-size: 4rem;
      color: darken(burlywood, 20%);
      border: none;
      cursor: pointer;

      transition: all 0.2s;

      &#prev {
        left: 0;
        transform: translateY(-50%) translateX(-150%);
      }
      &#next {
        right: 0;
        transform: translateY(-50%) translateX(+150%);
      }

      @media only screen and (max-width: vars.$bp-small) {
        font-size: 3rem;
        padding: 2rem;
      }

      &:hover {
        box-shadow: 0 1rem 2rem rgba(#333, 0.4);
        top: 49.5%;
      }

      &:active {
        box-shadow: none;
        top: 50%;
      }
    }
    .banner {
      display: block;
      position: absolute;
      width: 100%;
      object-fit: contain;
      top: 0;
      left: 0;
      opacity: 0;
      transition: opacity 1s ease-in-out;
    }

    .banner.active {
      opacity: 1;
    }

    @media only screen and (max-width: vars.$bp-medium) {
      width: 75svw;
      height: 50svw;
    }
  }
</style>
