```sv
<script>
  let initialOutline = "";
  let left = 0;
  let top = 0;
  let width = 0;
  let height = 0;
  let styleInfo = {
    fontSize: "",
    fontFamily: "",
    backgroundColor: "",
    color: "",
  };

  function mouseMove(e) {
    left = e.clientX + 10 + "px";
    top = e.clientY + 10 + "px";

    let { fontSize, fontFamily, backgroundColor, color } =
      window.getComputedStyle(e.target);

    styleInfo = {
      ...styleInfo,
      fontSize,
      fontFamily,
      backgroundColor,
      color,
    };

    width = e.target.getBoundingClientRect().width;
    height = e.target.getBoundingClientRect().height;

    e.target.style.outline = "black dashed 1px";
  }



  function mouseOver(e) {
    if (!e.target.style.outline) {
      initialOutline = window.getComputedStyle(e.target).outline;
    }
    initialOutline = e.target.style.outline;
  }

  function mouseLeave(e) {
    e.target.style.outline = initialOutline;
  }

  function click(e) {
    e.target.style.outline = initialOutline;
  }
</script>

<svelte:body
  on:mouseover={mouseOver}
  on:mouseout={mouseLeave}
  on:mousemove={mouseMove}
  on:click={click}
/>

<div class="tooltip" style:left style:top>
  <span><strong>Width</strong>: {width.toFixed(2)}</span>
  <span><strong>Height</strong>: {height.toFixed(2)}</span>
  <span><strong>Font size</strong>: {styleInfo.fontSize}</span>
  <span><strong>Font family</strong>: {styleInfo.fontFamily}</span>
  <span><strong>Background color</strong>: {styleInfo.backgroundColor}</span>
  <span><strong>Color</strong>: {styleInfo.color}</span>
</div>

<label>Label</label>
<input type="text" />

<div>
  <button class="btn">Button 1</button>
  <button class="btn">Button 2</button>
  <button class="btn">Button 3</button>
</div>

<style>
  .tooltip {
    position: absolute;
    display: flex;
    flex-direction: column;
    padding: 1rem;
    color: #fff;
    border-radius: 0.2rem;
    background-color: var(--dark);
    box-shadow: rgba(60, 64, 67, 0.15) 0px 2px 2px 0px,
      #ffffff26 0px 1px 3px 1px;
  }
</style>

```
