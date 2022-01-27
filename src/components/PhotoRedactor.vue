<template>
    <div id="main">
        <div class="flex">
            <div class="img-wrapper">
                <img src="../assets/img/cat.jpg" alt="">
            </div>
            <div class="controls">
                <h1>Shaverma-Cat</h1>
                <button>Showing/ Not</button>
            </div>
        </div>
    </div>    
</template>

<script>
export default {
    
}
</script>


<style  scoped>
  .container {
    margin-top: 40px;
  }
  .controls {
    margin-left: 20px;
  }
  .img-wrapper {
    width: 640px;
    height: 480px;
    background-color: #cecece;
  }
  img {
    transition: 0.2s ease;
   
  }
  button {
    margin-right: 10px;
    
  }
  h2 {
    margin-bottom: 10px;
  }
  .btn-group {
    margin-bottom: 20px;
  }
  input[type="range"] {
    display: block;
  }
</style>
