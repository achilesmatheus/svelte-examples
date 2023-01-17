<script>
  let dragging = false;
  let shiftX = 0;
  let shiftY = 0;
  let dropzone = null;
  let draggable = null;
  let currentDropzone = null;

  function dragStart(e) {
    e.preventDefault();
  }

  function mouseUp(e) {
    dragging = false;
    e.target.style.position = "static";

    currentDropzone.appendChild(e.target);
  }

  function mouseMove(e) {
    if (dragging && draggable) {
      draggable.style.position = "absolute";
      draggable.style.left = e.pageX - shiftX + "px";
      draggable.style.top = e.pageY - shiftY + "px";

      e.target.hidden = true;
      let elementBelow = document.elementFromPoint(e.clientX, e.clientY);
      e.target.hidden = false;

      if (elementBelow !== null) {
        if (elementBelow.classList.contains("dropzone")) {
          if (elementBelow === currentDropzone) {
            elementBelow.style.border = "2px solid";
          } else {
            elementBelow.style.border = "2px solid";
            currentDropzone.style.border = "none";
          }
          currentDropzone = elementBelow;
        }
      }
    }
  }

  function mouseDown(e) {
    dragging = true;
    draggable = e.target;
    let left = draggable.getBoundingClientRect().left;
    let top = draggable.getBoundingClientRect().top;

    shiftX = e.clientX - left;
    shiftY = e.clientY - top;

    currentDropzone = document.elementFromPoint(
      e.clientX,
      e.clientY
    ).parentElement;
  }
</script>

<svelte:body on:mousemove={mouseMove} />

<div class="wrapper">
  <div class="dropzone">
    <div
      class="card"
      on:mouseup={mouseUp}
      on:mousedown={mouseDown}
      on:dragstart={dragStart}
      draggable="true"
    >
      Item 1
    </div>

    <div
      class="card"
      on:mouseup={mouseUp}
      on:mousedown={mouseDown}
      on:mousemove={mouseMove}
      on:dragstart={dragStart}
      draggable="true"
    >
      Item 2
    </div>
  </div>

  <div class="dropzone" />
  <div class="dropzone" />
  <div class="dropzone" />
</div>

<style>
  .wrapper {
    display: flex;
    gap: 0.5rem;
  }

  .dropzone {
    height: 100px;
    width: 100px;
    background-color: #fff;
    border-radius: 0.2rem;
    box-shadow: rgba(60, 64, 67, 0.15) 0px 2px 2px 0px,
      #ffffff26 0px 1px 3px 1px;
    display: grid;
    place-content: center;
    gap: 0.5rem;
  }

  .card {
    padding: 0.5rem 1rem;
    margin: 0;
    background-color: #f8433f;
    color: #fff;
    cursor: move;
  }
</style>
