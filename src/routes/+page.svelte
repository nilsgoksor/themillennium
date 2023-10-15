<script>
  import { onMount } from "svelte";
  import "../app.css";
  import Celebrate from "$lib/Celebrate.svelte";
  import Spaceship from "$lib/Spaceship.svelte";

  let menuIndex = 0;

  let friendsAudio;
  let barbieAudio;
  let markoolioAudio;
  let wonderwallAudio;

  onMount(async () => {
    friendsAudio.play();
  });
</script>

<audio src="friends-theme.mp3" bind:this={friendsAudio} />
<audio src="barbie.mp3" bind:this={barbieAudio} />
<audio src="markoolio.mp3" bind:this={markoolioAudio} />
<audio src="wonderwall.mp3" bind:this={wonderwallAudio} />

<h1 class="animate-charcter">Y2K23</h1>
<Celebrate />
<div class="spaceship-container"><Spaceship /></div>
<div class="dvd" />

<main>
  <div class="menu">
    <button
      class="menu-button"
      class:selected={menuIndex === 0}
      on:click={() => (menuIndex = 0)}
    >
      Information
    </button>
    <button
      class="menu-button"
      class:selected={menuIndex === 1}
      on:click={() => (menuIndex = 1)}
    >
      Förfest
    </button>
    <button
      class="menu-button"
      class:selected={menuIndex === 2}
      on:click={() => (menuIndex = 2)}>FAQ</button
    >
    <a href="https://forms.gle/dB1ME3syTjMKrN8G6" target="_blank">
      <button class="menu-button">Anmälan</button></a
    >
  </div>
  {#if menuIndex === 0}
    <section>
      <p>
        Vi har alla länge funderat på den stora orättvisa som tilldelades vår
        generation, något som ingen av oss kunde göra något åt men som alla av
        oss drabbades av. Nu tycker vi att det är dags att göra något åt detta!
      </p>
      <p>
        Vi pratar självfallet om det faktum att vi aldrig fick fira
        milleniumskiftet ordentligt. Visst, många av oss var där och flera av
        oss har säkert minnen från denna stora stund, men handen på hjärtat:
        fick du verkligen fira på riktigt?
      </p>
      <p>
        Vi har nu tagit tillfället i akt och lytt det gamla ordspråket: “Det
        bästa tillfället att fira milleniumskiftet var när det begav sig, det
        nästa bästa tillfället är nu.” <a
          href="https://t.ly/5ICKk"
          target="_blank">(källa)</a
        >
      </p>
      <p>
        Så följ med oss den 2/12-23 i en kväll med halvkasst 90-talsmode,
        internet som mäts i kilobit/timme, och en stundande förväntan för vad
        det nya millenniet har att erbjuda!
      </p>
      <div>
        <button
          on:click={() => {
            friendsAudio.pause();
            markoolioAudio.pause();
            barbieAudio.pause();
            wonderwallAudio.play();
          }}>Alexander</button
        >
        <button
          on:click={() => {
            friendsAudio.pause();
            wonderwallAudio.pause();
            barbieAudio.pause();
            markoolioAudio.play();
          }}>Herman</button
        >
        <button
          on:click={() => {
            friendsAudio.pause();
            wonderwallAudio.pause();
            markoolioAudio.pause();
            barbieAudio.play();
          }}>Joel</button
        >
      </div>
    </section>
  {:else if menuIndex === 1}
    <section>Coming soon...!</section>
  {:else}
    <section>
      <p class="animate-charcter">
        Vad kul, jag vill med! Behöver jag göra något?
      </p>
      <p>
        Det kommer en länk till anmälan några veckor innan, sålänge du fyller i
        den och swishar betalning är allt klart!
      </p>
      <p class="animate-charcter">Varför kostar festen?</p>
      <p>Lokalkostnad + fri bar där man får vara kung om så önskas.</p>
      <p class="animate-charcter">
        Jag har en pojkvän/flickvän som gärna vill följa med, är det okej?
      </p>
      <p>
        Förmodligen! Skriv till Herman/Alexander/Joel och fråga, först till
        kvarn gäller eftersom lokalen har ett maxantal.
      </p>
      <p class="animate-charcter">Vilken är den bästa låten från 90-talet?</p>
      <p>
        Alexander - Wonderwall <br />
        Herman - Vi drar till fjällen <br />
        Joel - Barbie Girl.
      </p>
    </section>
  {/if}
</main>

<style>
  p {
    text-transform: uppercase;
    font-size: 1.75rem;
    font-weight: 700;
    background: -webkit-linear-gradient(#0ad1ad, #ea14c6);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  .menu {
    width: "100%";
    padding: 15px;
    background-color: grey;
    display: flex;
    margin-top: 65px;
    margin-bottom: 15px;
  }

  .menu-button {
    padding: 5px;
    margin: 5px;
  }
  .selected {
    color: blue;
  }

  .spaceship-container {
    position: absolute;
    height: 300;
    right: 175px;
    bottom: 190px;
    opacity: 0.5;
  }

  .dvd {
    width: 100px;
    height: 50px;
    background: url("../dvd.png");
    background-size: contain;
    background-repeat: no-repeat;
    position: absolute;
    z-index: 0;

    animation: toRight linear 12s infinite alternate,
      bounce linear 30s infinite alternate;
  }

  @keyframes bounce {
    0% {
      top: 0;
    }
    48% {
    }
    50% {
      top: calc(100% - 50px);
    }
    52% {
    }
    100% {
      top: 0;
    }
  }

  @keyframes toRight {
    0% {
      left: 0;
    }

    100% {
      left: calc(100% - 100px);
    }
  }

  h1 {
    font-size: 5rem;
  }

  .animate-charcter {
    text-transform: uppercase;
    background-image: linear-gradient(
      -225deg,
      #231557 0%,
      #44107a 29%,
      #ff1361 67%,
      #fff800 100%
    );
    background-size: auto auto;
    background-clip: border-box;
    background-size: 200% auto;
    color: #fff;
    background-clip: text;
    text-fill-color: transparent;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    animation: textclip 2s linear infinite;
    display: inline-block;
    margin: 0px;
  }

  @keyframes textclip {
    to {
      background-position: 200% center;
    }
  }
</style>
