<template>
  <main class="sponsor">
    <section class="hero">
      <div class="container">
        <div>
          <img src="@/assets/logo.svg" alt="AquaPerms">
          <font-awesome-layers>
            <font-awesome icon="heart" />
            <font-awesome icon="heart" />
          </font-awesome-layers>
          <img src="@/assets/aquasplashmc.svg" alt="AquasplashMC">
        </div>
        <h1>AquaPerms has partnered with AquasplashMC!</h1>
        <p>AquasplashMC is the best Minecraft Server that you can play on with your friends!
          We have only Earth for now, but we will also add Lifesteal and MiniGames soon!
          If you joined before 6/20 you will get a 20% store discount!</p>
      </div>
    </section>

    <section class="Inv ur friends :D">
      <div>
        <a href="https://discord.gg/xWNVTE7rp8" target="_blank" v-on:click="logClick">
          Play with your friends now!
        </a>
        <p>Click the link above to go to the AquasplashMC discord.</p>
      </div>
      <div>
        <a
          href="https://discord.gg/jMFgjhUt"
          target="_blank"
          v-on:click="logClick"
        >
          Chat to our support team.
        </a>
        <p>If you have any questions, use the button above to get in touch with the friendly
          AquasplashMC support team!
        </p>
      </div>
    </section>

    <div class="container">
      <section class="resources">
        <div>
          <h2>Why AquasplashMC?</h2>
          <ul>
            <li>
              AquasplashMC is a <strong>trusted</strong> and well established real minecraft experience and friendly
              community, and have already been serving a good experience for players.
            </li>
            <li>
              They provide an <strong>outstanding</strong> level of service we're happy to
              recommend.
            </li>
          </ul>
          <hr>
        </div>
        <div>
        </div>
      </section>
    </div>
  </main>
</template>

<script>

export default {
  name: 'Sponsor',
  metaInfo: {
    title: 'Sponsor',
  },
  data() {
    return {
    };
  },
  computed: {

  },
  methods: {
    logClick() {
      // eslint-disable-next-line no-undef
      plausible('SponsorLinkOut');
    },
  },
};
</script>

<style lang="scss">
  main.sponsor {
    overflow-y: auto;

    .hero {
      .container {
        display: flex;
        flex-direction: column;
        align-items: center;

        > div {
          display: flex;
          justify-content: center;
          align-items: center;
        }

        h1 {
          margin: 0 4rem 1rem;
          text-align: center;

          + p {
            font-size: 1.5rem;
            width: 100%;
            max-width: 60rem;
            text-align: center;
            margin-bottom: 4rem;
            padding: 0 2rem;
          }
        }
      }

      img {
        width: 8rem;
        margin: 2rem;

        @include breakpoint($md) {
          width: 16rem;
          margin: 4rem;
        }
      }

      .fa-layers {
        width: 2rem;

        @include breakpoint($md) {
          width: 8rem;
        }

        svg {
          font-size: 2rem;

          @include breakpoint($md) {
            font-size: 4rem;
          }

          &:first-child {
            color: red;
            animation: pulse 1s infinite ease-out;
          }

          &:last-child {
            color: hotpink;
            animation: heartbeat 1s infinite ease-out;
          }
        }
      }
    }

    hr {
      border-color: $brand-color;
      width: 12rem;
      margin: 1rem auto 2rem;
    }

    .cta {
      display: flex;
      //flex-direction: column;
      //align-items: center;
      //padding: 4rem;

      a {
        background: $brand-color;
        color: black;
        padding: .5rem 2rem;
        text-decoration: none;
        font-size: 2rem;
        font-weight: bold;
        margin: 2rem 0;
        text-align: center;
      }

      p {
        font-size: 1.5rem;
        width: 100%;
        max-width: 44rem;
        text-align: center;
        padding: 0 2rem;
      }
    }
  }

  @keyframes heartbeat {
    0% {
      transform: scale(1);
    }
    20% {
      transform: scale(1.2);
    }
  }

  @keyframes pulse {
    0% {
      transform: scale(1);
      opacity: .5;
    }
    100% {
      transform: scale(2.5);
      opacity: 0;
    }
  }
</style>
