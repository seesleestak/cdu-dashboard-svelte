<style>
  .frame {
    margin: 12px;
    padding: 12px;
    border: 1px solid white;
    border-radius: 2px;
    min-height: 300px;
    display: flex;
  }

  .row {
    margin: 0;
  }
</style>

<div class="row center-xs">
  <div class="col-xs-12 col-sm-11 col-md-9 col-lg-8 col-xl-6">
    <div class="frame">
      <slot />
    </div>
  </div>
</div>
