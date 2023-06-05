<script>
  import milo from './assets/milo.png';

  function addImage(e) {
    const miloImg = document.createElement('img');
    miloImg.src = milo;
    miloImg.style.width = '100px';
    miloImg.style.position = 'absolute';
    miloImg.style.left = e.clientX - 50 + 'px';
    miloImg.style.top = e.clientY - 50 + 'px';
    miloImg.style.animation = 'tiltHead 2.5s ease infinite';
    miloImg.style.zIndex = '0';
    console.log(e.clientX + ', ' + e.clientY);
    const box = document.getElementById('mainDiv');
    box.appendChild(miloImg);
  }
</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<div
  id="mainDiv"
  on:click={(e) => {
    addImage(e);
  }}
>
  <div class="center question">
    <p>Veux-tu être mon parrain ?</p>
  </div>
</div>

<style>
  #mainDiv {
    /* background-color: aqua; */
    position: absolute;
    width: 100%;
    height: 100vh;
  }
  .center {
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .question {
    /* background-color: pink; */
    width: 50%;
    margin-top: 20%;
    margin-left: 30%;
    z-index: 100;
    color: white;
    font-size: 5em;
    font-family: 'Gill Sans', sans-serif;
    position: absolute;
    text-align: center;
  }

  @keyframes tiltHead {
    0% {
      transform: rotate(0);
    }
    75% {
      transform: rotate(0);
    }
    80% {
      transform: rotate(3deg);
    }
    85% {
      transform: rotate(-3deg);
    }
    90% {
      transform: rotate(3deg);
    }
    95% {
      transform: rotate(-3deg);
    }
    100% {
      transform: rotate(0);
    }
  }
</style>
