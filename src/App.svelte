<script>
  import Music from "./assets/music.mp4";
  import VideoFile from "./assets/brainpepe.mp4";
  import Banner from "./assets/banner.png";
  import Logo from "./assets/pepebrain.png";
  import Logo2 from "./assets/logo2.png";
  import BG from "./assets/bg.png";

  let videoRef;

  function enableSound() {
    if (videoRef) {
      videoRef.muted = false;
      if (videoRef.paused) {
        videoRef.play();
      }
    }
  }

  function redirectBuyLink() {
  window.open(
    'https://pulsex.mypinata.cloud/ipfs/bafybeiesh56oijasgr7creubue6xt5anivxifrwd5a5argiz4orbed57qi/#/?outputCurrency=0xa6Ca9975568f22C4156f8c94D41C40fa590812C3',
    '_blank'
  );
}

function redirectTgLink() {
  window.open(
    'https://t.me/+WR2-aOv3iElkNWY6',
    '_blank'
  );
}

function rediredtReounceLink() {
  window.open(
    'https://bafybeicb2hlad6zs4kc4yvn5xbbzti6krjtpoxrysg42d4e5s5oubbipum.ipfs.dweb.link/#/tx/0xf04ee77bd94f143bddc258b80ff90c65ac660a63e57742f5ce7cee4822f5ca0c',
    '_blank'
  );
}

</script>

<svelte:window on:click={enableSound} on:keydown={enableSound} />


<div style="background-image: url({BG}); background-size: cover; background-repeat: no-repeat; background-position: center; margin-left: -1rem; width: 101%;">


<img class="banner" src={Banner} alt="Banner description" />

<!-- Some browsers might refuse to play music upon key tap, so we try to do it via both onMount and also keyDown -->

<video
  bind:this={videoRef}
  autoplay
  loop
  muted
  playsinline
  style="display: none;"
>
  <source src={Music} type="video/mp4" />
  Your browser does not support the video tag.
</video>

<div id="container">
  <video autoplay loop muted playsinline id="backgroundVideo">
    <source src={VideoFile} type="video/mp4" />
    Your browser does not support the video tag.
  </video>
</div>

  <div id="btnContainer">
    <img class="logo" src={Logo} alt="Logo" />
    <button class="fancy-button" on:click={redirectBuyLink}>BUY BUY BUY</button>
  </div>
  
  <div id="btnContainer">
    <img class="logo" src={Logo} alt="Logo" />
    <button class="fancy-button" style="line-height: 2.5rem;" on:click={redirectTgLink}>TELEGRAM TELEGRAM TELEGRAM</button>
  </div>
  
  <div id="btnContainer">
    <img class="logo" src={Logo} alt="Logo" />
    <button class="fancy-button" style="line-height: 2.5rem;" on:click={rediredtReounceLink}>RENOUNCED RENOUNCED RENOUNCED</button>
  </div>
  
  <div id="btnContainer">
    <img class="logo" src={Logo2} alt="Logo" />
    <button class="fancy-button" style="padding: 1 2rem; min-width: 36rem;"> CA: 0xa6ca9975568f22c4156f8c94d41c40fa590812c3 </button>
  </div>

<br>
<br>
<br>

<div id="dexscreener-embed">
  <iframe
    src="https://dexscreener.com/pulsechain/0x478d2baBB03D60f83Bc9c76E5Ce2aE529d6e996a?embed=1&theme=dark"
  ></iframe>
</div>

<br>
<br>
<br>
<br>

</div>

<style>

  #dexscreener-embed {
    position: relative;
    margin: 0 auto;
    width: 70%;
    padding-bottom: 125%;
    z-index: 2;
  }
  @media (min-width: 1400px) {
    #dexscreener-embed {
      padding-bottom: 65%;
    }
  }
  #dexscreener-embed iframe {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    border: 0;
  }

  .banner {
    display: block;
    margin: 0 auto;
    position: relative;
    padding: 0;
    z-index: 2;
    width: 100vw;
    height: auto;
    max-height: 800px;
    margin-top: -1rem;
  }

  #container {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 60vh;
  }

  #btnContainer {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 30vh;
  }

  #backgroundVideo {
    min-width: 50%;
    min-height: 50%;
    width: auto;
    height: auto;
    z-index: -100;
    object-fit: cover;
    background-size: cover;
    overflow: hidden;
    z-index: 1;
  }

  @keyframes rainbow-color {
    0% {
      background-color: red;
    }
    15% {
      background-color: orange;
    }
    30% {
      background-color: yellow;
    }
    45% {
      background-color: green;
    }
    60% {
      background-color: blue;
    }
    75% {
      background-color: indigo;
    }
    90% {
      background-color: violet;
    }
    100% {
      background-color: red;
    }
  }

  .logo {
    width: 10rem;
    height: auto;
  }

  .fancy-button {
    width: calc(25% + 5rem);
    padding: 1rem 2rem;
    font-size: 1.5em;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    outline: none;
    animation: rainbow-color 1s linear infinite;
  }

  .fancy-button:hover {
    transform: scale(1.1);
  }

  @media (max-width: 768px) {

    #btnContainer {
      height: 35rem;
      flex-direction: column;
    }

    .logo,
    .fancy-button {
      margin: 0 auto;
      width: calc(15% + 10rem);
    }

  }
</style>
