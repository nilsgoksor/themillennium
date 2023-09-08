<script>
  import { writable } from "svelte/store";

  const gifSources = [
    "https://media.giphy.com/media/l2JJyDYEX1tXFmCd2/giphy.gif",
    "https://media.giphy.com/media/bznNJlqAi4pBC/giphy.gif",
    "https://media.giphy.com/media/YnBntKOgnUSBkV7bQH/giphy.gif",
    "https://media.giphy.com/media/lPoxtQlcX30doRbHTN/giphy.gif",
  ];

  let tick = writable(0, () => {
    let interval = setInterval(() => {
      tick.update((value) => {
        if (value === gifSources.length - 1) return 0;
        return value + 1;
      });
    }, 5000);

    return () => {
      clearInterval(interval);
    };
  });
</script>

<div class="celebrate">
  <img class="celebrate-img" src={gifSources[$tick]} alt="" />
  <img class="celebrate-img" src={gifSources[$tick]} alt="" />
  <img class="celebrate-img" src={gifSources[$tick]} alt="" />
  <img class="celebrate-img" src={gifSources[$tick]} alt="" />
  <img class="celebrate-img" src={gifSources[$tick]} alt="" />
  <img class="celebrate-img" src={gifSources[$tick]} alt="" />
</div>

<style>
  .celebrate {
    display: flex;
    justify-content: center;
    position: absolute;
    overflow: hidden;
    top: 0;
    width: 100%;
    max-width: 700px;
    margin: auto;
    opacity: 0.4;
  }
  .celebrate-img {
    height: 155px;
  }

  @media screen and (max-width: 600px) {
    .celebrate {
      left: 0px;
    }
  }
</style>
