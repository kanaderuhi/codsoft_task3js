<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Digital Clock</title>
      <style>
        body 
        {
          font-family: Arial, sans-serif;
          background-color: #d2d9a0;
        }
        
        .clock-container 
        {
          display: flex;
          justify-content: center;
          align-items: center;
          height: 100vh;
        }
        
        .clock 
        {
          font-size: 75px;
          font-weight: bold;
          color: #272728;
        }
        
        .clock span 
        {
          margin: 0 10px;
        }
      </style>
  </head>
  <body>
    <div class="clock-container">
      <div class="clock">
        <span id="hours">00</span>
        <span>:</span>
        <span id="minutes">00</span>
        <span>:</span>
        <span id="seconds">00</span>
      </div>
    </div>
    <script>
      const hoursElement = document.getElementById('hours');
      const minutesElement = document.getElementById('minutes');
      const secondsElement = document.getElementById('seconds');

      function updateTime() 
      {
        const currentTime = new Date();
        const hours = currentTime.getHours();
        const minutes = currentTime.getMinutes();
        const seconds = currentTime.getSeconds();

        hoursElement.textContent = padZero(hours);
        minutesElement.textContent = padZero(minutes);
        secondsElement.textContent = padZero(seconds);
      }

      function padZero(time) 
      {
        return (time < 10 ? '0' : '') + time;
      }

       setInterval(updateTime, 1000);
    </script>
  </body>
</html>
