<script>
  const menuItems = ['Home', 'Chi siamo', 'Servizi', 'Contatti', 'Promozioni'];
</script>

<header class="header">
  <img
    src="https://media.istockphoto.com/id/1483860812/it/foto/primo-piano-del-girasole-nel-campo-di-girasole-cielo-blu-sullo-sfondo-tema-fiori-primaverili.webp?b=1&s=170667a&w=0&k=20&c=REpMBl2XNagrVojRw-vrNuEmeLoM0aNvdP9RYxGMQdQ="
    id="logo"
    alt="logo" />

  <ul class="nav" id="nav">
    {#each menuItems as item (item)}
      <li class="nav__item">
        <a class="nav__link" href="#">{item}</a>
      </li>
    {/each}
  </ul>

  <div class="login">
    <a class="login__link" href="#"
      >Sign in
      <!-- <img src="utente.png" id="logo_utente"
    /> -->
    </a>
    <a class="login__link" href="#"
      >Sign up
      <!-- <img src="utente.png" id="logo_utente"
    /> -->
    </a>
  </div>

  <div id="menu-btn">
    <div class="menu"></div>
  </div>
</header>

<style lang="scss">
  @use '../styles/vars';

  .header {
    display: flex;
    background-color: burlywood;
    height: 10rem;
    align-items: center;
    position: relative;
    overflow: hidden;

    #logo {
      max-height: 100%;
      margin-right: 5rem;

      @media only screen and (max-width: vars.$bp-small) {
        margin-right: 2rem;
      }
    }
    .nav {
      display: flex;
      align-items: center;
      flex-wrap: wrap;
      position: static;
      box-shadow: none;
      padding: 0;
      background-color: burlywood;
      list-style: none;
      z-index: 10;

      @media only screen and (max-width: vars.$bp-medium) {
        flex-direction: column;
        padding: 3rem;
        box-shadow: 0 1rem 2rem rgba(#000, 0.15);
        position: absolute;
        top: 10rem;
        right: 0;
        transform: translateX(100%);
        border-radius: 3px;
        transition: all 0.5s;

        &.showNav {
          transform: translateX(0);
        }
      }

      &__item {
        text-align: center;

        &:not(:last-child) {
          margin-right: 2rem;

          @media only screen and (max-width: vars.$bp-medium) {
            margin-right: 0;
          }
        }
      }

      &__link:link,
      &__link:visited {
        display: none;
        font-size: 2.3rem;
        text-decoration: none;
        text-transform: uppercase;
        display: block;
        padding: 1rem 2rem;
        color: #000;
        transition: all 0.2s;
        border-radius: 5px;
      }

      &__link:hover {
        transform: translateY(-3px) scale(1.05);
        box-shadow: 0 1rem 2rem rgba(#000, 0.4);
        background-color: darken(burlywood, 5%);
      }

      &__link:active {
        transform: translateY(0) scale(1);
        box-shadow: none;
        background-color: burlywood;
      }
    }

    .login {
      font-size: 2.2rem;
      margin-left: auto;
      margin-right: 2rem;

      margin-right: 3rem;

      @media only screen and (max-width: vars.$bp-small) {
        margin-right: 0;
        text-align: center;
      }

      &__link:link,
      &__link:visited {
        color: #000;
        text-decoration: none;
        display: inline-block;
        padding: 1rem 2rem;
        transition: all 0.2s;
        border-radius: 5px;
        &:not(:last-child) {
          margin-right: 3rem;
          @media only screen and (max-width: vars.$bp-small) {
            margin-right: 0;
          }
        }
      }

      &__link:hover {
        transform: translateY(-3px) scale(1.05);
        box-shadow: 0 1rem 2rem rgba(#000, 0.4);
        background-color: darken(burlywood, 5%);
      }

      &__link:active {
        transform: translateY(0) scale(1);
        box-shadow: none;
        background-color: burlywood;
      }
    }
  }
  #menu-btn {
    cursor: pointer;
  }
</style>
