<div class="rocket">
  <div class="fuselage">
    <div class="nose" />
    <div class="head">
      <span class="window" />
    </div>
    <div class="neck" />
    <div class="body" />
    <div class="reactor" />
    <div class="fire">
      <div class="spark1" />
      <div class="spark2" />
      <div class="spark3" />
      <div class="spark4" />
      <div class="spark5" />
      <div class="spark6" />
    </div>
  </div>
  <div class="left-fin" />
  <div class="left-fin-end" />
  <div class="right-fin" />
  <div class="right-fin-end" />
</div>

<style>
  .rocket {
    width: 50px;
    margin: 0 auto;
    transition: transform 0.2s ease-in-out;
  }

  .fuselage {
    width: 50px;
  }

  .nose {
    width: 25px;
    margin: 0 auto;
    border-top: 15px solid #353535;
    border-top-left-radius: 50%;
    border-top-right-radius: 50%;
  }

  .head {
    possition: relative;
    display: block;
    border-bottom: 25px solid white;
    border-left: 10px solid transparent;
    border-right: 10px solid transparent;
    height: 0;
    width: 25px;
    margin: 0 auto;
  }

  .window {
    position: absolute;
    top: 16px;
    left: 10px;
    border-bottom: 15px solid #00a0d6;
    border-left: 5px solid transparent;
    border-right: 5px solid transparent;
    height: 0;
    width: 20px;
  }

  .neck {
    position: relative;
    width: 45px;
    height: 30px;
    margin: 0 auto;
    background: #f4f4f4;

    &:after {
      position: absolute;
      top: 0;
      right: 0;
      content: "";
      width: 22.5px;
      height: 30px;
      background: #e0e0e0;
    }
  }

  .body {
    position: relative;
    width: 50px;
    height: 120px;
    background: #f4f4f4;
    border-bottom: 3px solid #a81237;
    border-top: 3px solid #a81237;

    &:after {
      position: absolute;
      top: 0;
      right: 0;
      content: "";
      width: 25px;
      height: 120px;
      background: #e0e0e0;
    }
  }

  .reactor {
    position: relative;
    border-bottom: 30px solid #4f4f4f;
    border-left: 10px solid transparent;
    border-right: 10px solid transparent;
    height: 0;
    width: 30px;
    margin: 0 auto;

    &:after {
      content: "";
      position: absolute;
      top: 0;
      left: -10px;
      width: 15px;
      opacity: 0.3;
      border-bottom: 30px solid #e0e0e0;
      border-left: 10px solid transparent;
    }
  }

  .fire {
    position: relative;
    width: 25px;
    height: 70px;
    margin: 0 auto;
    border-bottom-right-radius: 50%;
    border-bottom-left-radius: 50%;
    animation: fire 0.2s infinite;
  }

  .spark1 {
    top: 30px;
    left: 5px;
    width: 40px;
    height: 40px;
    border-radius: 50%;
    animation: fireBig 0.5s infinite;
  }

  .spark2 {
    top: 35px;
    right: 5px;
    width: 20px;
    height: 20px;
    border-radius: 50%;
    animation: fireBig 0.3s infinite;
  }

  .spark3 {
    top: 40px;
    right: 20px;
    width: 50px;
    height: 50px;
    border-radius: 50%;
    animation: fireSmall 0.4s infinite;
  }

  .spark4 {
    top: 40px;
    left: -20px;
    width: 30px;
    height: 30px;
    border-radius: 50%;
    animation: fireSmall 0.7s infinite;
  }
  .spark5 {
    top: 30px;
    right: -10px;
    width: 10px;
    height: 10px;
    border-radius: 50%;
    animation: fireSmall 0.6s infinite;
  }
  .spark6 {
    top: 60px;
    left: 5px;
    width: 10px;
    height: 10px;
    border-radius: 50%;
    animation: fireSmall 0.2s infinite;
  }

  .left-fin {
    position: absolute;
    top: 73px;
    right: 50px;
    width: 5px;
    border-bottom: 110px solid white;
    border-left: 60px solid transparent;

    &-end {
      position: absolute;
      top: 113px;
      right: 70px;
      border-bottom: 70px solid white;
      border-left: 70px solid transparent;
      border-top-left-radius: 50%;
      border-bottom-left-radius: 10%;
    }
  }

  .right-fin {
    position: absolute;
    top: 73px;
    left: 50px;
    width: 5px;
    border-bottom: 110px solid white;
    border-right: 60px solid transparent;

    &-end {
      position: absolute;
      top: 113px;
      left: 70px;
      border-bottom: 70px solid white;
      border-right: 70px solid transparent;
      border-bottom-right-radius: 10%;
    }

    &:after {
      content: "";
      z-index: 2;
      position: absolute;
      top: 0;
      left: 0;
      width: 4px;
      border-bottom: 110px solid #c4c4c4;
      border-right: 10px solid transparent;
    }
  }

  .rocket:hover {
    transform: translate3d(30px, -30px, 30px) rotateY(30deg);
  }

  @keyframes fire {
    0% {
      background: linear-gradient(
        to bottom,
        rgba(255, 134, 28, 1) 0%,
        rgba(239, 1, 124, 1) 50%,
        rgba(237, 3, 3, 1) 100%
      );
    }
    50% {
      background: linear-gradient(
        to bottom,
        rgba(237, 3, 3, 1) 0%,
        rgba(255, 134, 28, 1) 51%,
        rgba(239, 1, 124, 1) 100%
      );
    }
    100% {
      background: linear-gradient(
        to bottom,
        rgba(239, 1, 124, 1) 0%,
        rgba(237, 3, 3, 1) 51%,
        rgba(255, 134, 28, 1) 100%
      );
    }
  }

  @keyframes fireBig {
    0% {
      width: 10px;
      height: 10px;
      background: #ff861c;
    }
    50% {
      background: #ef017c;
    }
    100% {
      width: 60px;
      height: 60px;
    }
  }

  @keyframes fireSmall {
    0% {
      width: 10px;
      height: 10px;
      background: #ff861c;
    }
    50% {
      background: #ef017c;
    }
    100% {
      width: 40px;
      height: 40px;
    }
  }

  @keyframes stars {
    0% {
      top: -100%;
    }
    100% {
      top: 0;
    }
  }
</style>
