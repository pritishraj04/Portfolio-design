<script>
  export let char;

  let isPressed = false;

  const keyPress = () => {
    isPressed = true;
    setTimeout(() => {
      isPressed = false;
    }, 200);
  };

  function handleWindowKeyDown(event) {
    if (event.key === char) {
      keyPress();
    }
  }
</script>

<svelte:window on:keydown={handleWindowKeyDown} />

<span
  on:mousedown={() => keyPress()}
  style={isPressed ? "transform: scale(0.9)" : "transform: scale(1)"}
  ><i>{char}</i></span
>

<style lang="scss">
  :first-child {
    grid-column: 1 / span 3;
    justify-self: center;
  }
  span {
    position: relative;
    display: inline-block;
    font-family: consolas;
    width: 80px;
    height: 80px;
    padding: 8px;
    border-radius: 10px;
    background: linear-gradient(180deg, #282828, #202020);
    box-shadow: inset -8px 0 8px rgba(0, 0, 0, 0.15),
      inset 0 -8px 8px rgba(0, 0, 0, 0.25), 0 0 0 2px rgba(0, 0, 0, 0.4),
      10px 20px 25px rgba(0, 0, 0, 0.4);
    overflow: hidden;
    &::before {
      content: "";
      position: absolute;
      top: 3px;
      left: 4px;
      bottom: 14px;
      right: 12px;
      background: linear-gradient(90deg, #232323, #4a4a4a);
      border-radius: 10px;
      box-shadow: -10px -10px 10px rgba(255, 255, 255, 0.25),
        10px 5px 10px rgba(0, 0, 0, 0.15);
      border-left: 1px solid #0004;
      border-bottom: 1px solid #0004;
      border-top: 1px solid #0009;
    }
    i {
      position: relative;
      color: #fff;
      font-style: normal;
      text-transform: uppercase;
      -webkit-touch-callout: none;
      -webkit-user-select: none;
      -khtml-user-select: none;
      -moz-user-select: none;
      -ms-user-select: none;
      user-select: none;
    }
  }
</style>
