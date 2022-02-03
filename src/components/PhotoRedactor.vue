<template>
    <div id="photo" class="containter">
        <div class="flex">
            <div class="img-wrapper">
                <img src="../assets/cat.jpg"
                :class="imgFilters" 
                v-show="isCatVisible" 
                :style="imgStyles">
                <!-- <p v-else>Hello Cat</p> -->
            </div>
            <div class="controls">
                <h1>Shaverma-Cat</h1>
                <h2>Filters</h2>
                <div class="btn-group ">
                    <button 
                @click="isCatVisible = !isCatVisible"
                >
                    {{ isCatVisible ? 'Not Showing' : 'Showing'}} 
                </button>
             
                <button 
                :class="imgFilters.sepia ? 'active' : ''"
                @click="imgFilters.sepia = !imgFilters.sepia">
                    Sepia
                </button>
                <button 
                :class="imgFilters.border ? 'active' : ''"
                @click="imgFilters.border = !imgFilters.border">
                    Border
                </button>
                <button 
                @click="imgFilters.small = !imgFilters.small">
                    {{ imgFilters.small ? 'Large' : 'Small' }}
                </button>
                
                </div>

                <h2>Img Size</h2>

                <div class="btn-group">
                    <label for="">
                        Width:  {{ imgSizes.currentWidth }}
                        <input 
                        type="range"
                        :value="imgSizes.currentWidth"
                        @input="imgSizes.currentWidth = $event.target.value"
                        :min="imgSizes.minWidth"
                        :max="imgSizes.maxWidth"
                        >
                    </label>
                    <label for="">
                        Height:  {{ imgSizes.currentHeight }}
                        <input 
                        type="range"
                        :value="imgSizes.currentHeight"
                        @input="imgSizes.currentHeight = $event.target.value"
                        :min="imgSizes.minHeight"
                        :max="imgSizes.maxHeight"
                        >
                    </label>


                </div>

                

            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'PhotoRedactor',
    data() {
        return {
            isCatVisible: true,
            imgFilters: {
                border: false,
                sepia: false,
                small: false,
            },
            imgSizes: {
                maxWidth: 640,
                maxHeight: 480,
                currentWidth: 640,
                currenHeight: 480,
            },
            isActive: false,
        }
    },
    computed: {
        imgStyles() {
            return {
                width: `${this.imgSizes.currentWidth}px`,
                height: `${this.imgSizes.currentHeight}px`,
            }
        }
    }
}
</script>

<style scoped>
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
    padding: 5px 8px;
    background: #fff;
    border:2px solid rgba(0, 0, 0, 0.568);
    border-radius: 5px;
    cursor: pointer;
    transition: .2s linear all;
  }
  .active {
      background: #f5f5f5 !important;
  }
  button:hover {
      background: #f1f1f1 !important;
  }
  h2 {
    margin-bottom: 10px;
  }
  .btn-group {
    margin-top: 20px;
  }
  input[type="range"] {
    display: block;
  }
  .flex {
      display: flex;
      margin-left: 120px;
  }

  .sepia {
        filter: sepia(100%);
    }
  .border {
        border: 5px dashed #464646
    }
  .small {
        width: 400px;
   }


</style>