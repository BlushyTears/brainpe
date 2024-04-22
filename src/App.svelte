<script>

  import Counter from './lib/Counter.svelte'
  import Music from './assets/music.mp4';
  import VideoFile from './assets/brainpepe.mp4';
  import Banner from './assets/banner.png';
  import Logo from './assets/pepebrain.png';

  let videoRef;

  function enableSound() {
    if (videoRef) {
      videoRef.muted = false;
      if (videoRef.paused) {
        videoRef.play();
      }
    }
  }

</script>

<img class='banner' src={Banner} alt="Banner description" />

 <!-- Some browsers might refuse to play music upon key tap, so we try to do it via both onMount and also keyDown -->
<svelte:window on:click={enableSound} on:keydown={enableSound}/>

<video bind:this={videoRef} autoplay loop muted playsinline style="display: none;">
  <source src={Music} type="video/mp4">
  Your browser does not support the video tag.
</video>

<video autoplay loop muted playsinline id="backgroundVideo">
  <source src={VideoFile} type="video/mp4">
  Your browser does not support the video tag.
</video>


<div class="container">
  <img class="logo" src={Logo} alt="Logo">
  <button class="fancy-button">BUY BUY BUY</button>
</div>

<style>

.banner {
  display: block;    
  margin: 0 auto;    
  position: relative;
  z-index: 2;
  width: calc(30vw + 10rem);
  height: auto;
  margin-top: -1rem;
}

#backgroundVideo {
    position: fixed; 
    right: 0;
    bottom: 0;
    min-width: 100%; 
    min-height: 100%;  
    width: auto;
    height: auto;  
    z-index: -100; 
    object-fit: cover;  
    background-size: cover;
    overflow: hidden;
    z-index: 1; 
  }

  @keyframes rainbow-color {
    0% { background-color: red; }
    15% { background-color: orange; }
    30% { background-color: yellow; }
    45% { background-color: green; }
    60% { background-color: blue; }
    75% { background-color: indigo; }
    90% { background-color: violet; }
    100% { background-color: red; }
  }

  .container {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  height: 30vh; 
  width: 95vw;   
  position: relative;
  background: none; 
  z-index: 1; 
}

  .logo {
    width: 10rem; 
    height: auto;
  }

  .fancy-button {
    width: calc(25% + 5rem);
    padding: 2rem 5rem;
    font-size: 2em;
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
  .container {
    height: 30rem; 
    flex-direction: column;
  }

  .logo, .fancy-button {
    margin: 0 auto;  
  }
}

  
</style>

