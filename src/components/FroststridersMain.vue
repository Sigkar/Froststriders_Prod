<template>
  <div class="Froststriders">
    <div class="center" id="content">
      PROJECT:
      <br/>
      <div id="target">&nbsp;</div>
    </div>
  </div>
</template>

<script>
    const OutputFinal = "FROSTSTRIDERS";
  const delay = 75;
  const loops = 20;

  let output, html, len;


  function jumble(_current, _len) {
    let text;
    _current.length>0 ? text = _current + "<span id='blinker'>|</span>" : text = _current;
    let possible = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789";
    for (var i = 0; i < (_len - _current.length); i++)
      text += possible.charAt(Math.floor(Math.random() * possible.length));
    return text;
  }

  async function intro () {
    let j = 0;
    while(j<=loops){
      j++;
      await sleep(delay);
      loadText(jumble("", len), "target");
    }
    return 0;
  }

  async function blink (){
    let open;
    window.setInterval(function () {
        if(open){
          document.getElementById("blinker").innerHTML = " |";
          open = false;
        }else{
          document.getElementById("blinker").innerHTML = "";
          open = true;
        }
    }, 400); // repeat forever, polling every 3 seconds
  }

  async function createText (){
      await sleep(loops * delay);
      for(let i = 1; i <= len; i++){
        loadText(jumble(output.substring(0, i), len), "target")
        await sleep(delay);
      }
  }

  function sleep(ms) {
    return new Promise(resolve => setTimeout(resolve, ms));
  }


  function loadText(_output, target) {
    html = _output;
    document.getElementById(target).innerHTML = html;
  }

  function doit(){
    output = OutputFinal;
    len = OutputFinal.length;
    intro().then(createText());
  }

  document.addEventListener("DOMContentLoaded", function() {
    blink();
    doit();
  });
  export default {
    name: 'FroststridersMain',
    props: {
      msg: String
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url("https://fonts.googleapis.com/css?family=Unica+One");
* {
  color: #fceff9;
  font-family: "Unica One", monospace;
}
.center {
  font-size: 60px;
  font-weight: bold;
  width: 70%;
  position: absolute;
  top: 30%;
  left: 20%;
  word-wrap: break-word;
}
#target {
  text-transform: uppercase;
  letter-spacing: 8px;
  font-size: 40px;
  color: white;
}

#reset {
  position: fixed;
  top: 0px;
  left: 0px;
  border: none;
  outline: none;
  background-color: black;
  font-size: 24px;
  cursor: pointer;
}
#reset:hover {
  background: #2c2c2c;
}

@media screen and (max-width: 700px) {
  .center {
    width: 90%;
    left: 5%;
  }
  #target{
    letter-spacing:5px;
  }
}
</style>
