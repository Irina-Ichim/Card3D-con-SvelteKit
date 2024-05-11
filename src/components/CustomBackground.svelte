
<script>
    export let className;
  </script>
  
  <style>
    .custom-background {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      overflow: hidden;
      pointer-events: none;
      z-index: 0;
    }
  
    .gradient {
      position: absolute;
      top: 0;
      left: 0;
      width: 200%;
      height: 200%;
      transform: translate(-50%, -50%);
      pointer-events: none;
    }
  
    
    @keyframes moveHorizontal {
      0% {
        transform: translateX(-50%) translateY(-10%);
      }
      50% {
        transform: translateX(50%) translateY(10%);
      }
      100% {
        transform: translateX(-50%) translateY(-10%);
      }
    }
  

    .gradient.first {
      animation: moveHorizontal 30s ease infinite;
      background: radial-gradient(circle at center, rgba(18, 113, 255, 0.8) 0, rgba(18, 113, 255, 0) 50%);
    }
  
    .gradient.second {
      animation: moveInCircle 20s reverse infinite;
      background: radial-gradient(circle at center, rgba(221, 74, 255, 0.8) 0, rgba(221, 74, 255, 0) 50%);
    }
  
    .gradient.third {
      animation: moveVertical 40s linear infinite;
      background: radial-gradient(circle at center, rgba(100, 220, 255, 0.8) 0, rgba(100, 220, 255, 0) 50%);
    }
  
    
    @keyframes moveHorizontal {
      0% {
        transform: translateX(-50%) translateY(-10%);
      }
      50% {
        transform: translateX(50%) translateY(10%);
      }
      100% {
        transform: translateX(-50%) translateY(-10%);
      }
    }
  
    @keyframes moveInCircle {
      0% {
        transform: rotate(0deg);
      }
      50% {
        transform: rotate(180deg);
      }
      100% {
        transform: rotate(360deg);
      }
    }
  
    @keyframes moveVertical {
      0% {
        transform: translateY(-50%);
      }
      50% {
        transform: translateY(50%);
      }
      100% {
        transform: translateY(-50%);
      }
    }
  
  </style>
  
  <div class="{className} custom-background">
    
    <div class="gradient first"></div>
    <div class="gradient second"></div>
    <div class="gradient third"></div>
  </div>
  