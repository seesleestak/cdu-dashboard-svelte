<script>
  const value = 0;
  function getNeedlePosition(value) {
    // Gauge limits with estimated min and max temperatures
    // for all time, based on local weather
    const min = 20;
    const max = 115;

    // Degree position min and max
    const gaugeMax = 170;
    const gaugeMin = -90;

    // Linear interpolation with the value
    return ((value - min) * (gaugeMax - gaugeMin)) / (max - min) + gaugeMin;
  }
</script>

<style>
  .gauge {
    position: relative;
    border: 2px solid white;
    border-radius: 50%;
    height: 75px;
    width: 75px;
    margin: 0 auto 8px;
  }

  .gauge-temp {
    position: absolute;
    right: -32px;
    bottom: -10px;
  }

  .gauge-temp-cont {
    position: absolute;
    height: 50px;
    width: 50px;
    right: -12px;
    bottom: -6px;
    background-color: #121213;
  }

  .needle {
    position: absolute;
    height: 4px;
    border-radius: 2px;
    width: 28px;
    margin-right: 21px;
    bottom: 50%;
    right: 50%;
    z-index: 2;
    background-color: #a7e851;
    transform-origin: 175% 50%;
  }
</style>

<div class="gauge">
  <div
    style={`transform: rotate(${getNeedlePosition(value)}deg)`}
    class="needle" />
  <div class="gauge-temp-cont" />
  <div class="gauge-temp">
    <slot />
  </div>
</div>
