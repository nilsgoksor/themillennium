<script>
  import { onMount } from "svelte";
  import "../app.css";
  import Celebrate from "$lib/Celebrate.svelte";
  import Spaceship from "$lib/Spaceship.svelte";


  let audio;
  onMount(async () => {
    // audio.play();
  });
</script>

<h1 class="animate-charcter">Y2K2023</h1>
<Celebrate />
<div class="spaceship-container"><Spaceship /></div>
<section>
  <p>
    Vi har alla länge funderat på den stora orättvisa som tilldelades vår
    generation, något som ingen av oss kunde göra något åt men som alla av oss
    drabbades av. Nu tycker vi att det är dags att göra något åt detta!
  </p>
  <p>
    Vi pratar självfallet om det faktum att vi aldrig fick fira milleniumskiftet
    ordentligt. Visst, många av oss var där och flera av oss har säkert minnen
    från denna stora stund, men handen på hjärtat: fick du verkligen fira på
    riktigt?
  </p>
  <p>
    Vi har nu tagit tillfället i akt och lytt det gamla ordspråket: “Det bästa
    tillfället att fira milleniumskiftet var när det begav sig, det nästa bästa
    tillfället är nu.” [Källa: https://t.ly/5ICKk]
  </p>
  <p>
    Så följ med oss den 2/12-23 i en kväll med halvkasst 90-talsmode, internet
    som mäts i kilobit/timme, och en stundande förväntan för vad det nya
    millenniet har att erbjuda!
  </p>
  <p>//Alexander, Herman, Joel</p>
</section>
<audio src="friends-theme.mp3" bind:this={audio} />

<style>
  p {
    text-transform: uppercase;
    font-size: 2rem;
    background: -webkit-linear-gradient(#0ad1ad, #ea14c6);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }
  .spaceship-container {
    position: absolute;
    height: 300;
    right: 175px;
    top: 20px;
    opacity: 0.5;
  }
</style>
