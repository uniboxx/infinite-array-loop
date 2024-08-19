<div id="backdrop"></div>

<style lang="scss">
  @use '../styles/vars';

  #backdrop {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100svh;
    backdrop-filter: blur(0);
    z-index: 5;
    pointer-events: none;
    transition: all 0.5s;

    &.showBackdrop {
      pointer-events: all;
      backdrop-filter: blur(5px);
    }
  }
</style>
