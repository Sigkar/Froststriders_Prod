<template>
  
  <Box class="box" :pose="isVisible ? 'visible' : 'hidden'">
    <div class="Froststriders_Cover" >
      
      <div class="center" id="content">
        PROJECT:
        <br/>
        <div id="target">&nbsp;</div>
      </div>
    </div>
  </Box>
</template>

<script>
  import posed from 'vue-pose';

  const OutputFinal = "FROSTSTRIDERS_TLAIR.INI()";
  const delay = 75;
  const loops = 20;
  let html;

  function jumble(_current, _len) {
    let text;
    _current.length>0 ? text = _current + "<span id='blinker'>█</span>" : text = _current;
    let possible = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789";
    for (let i = 0; i < (_len - _current.length); i++)
      text += possible.charAt(Math.floor(Math.random() * possible.length));
    return text;
  }
  
  async function intro (_len) {
    let j = 0;
    while(j<=loops){
      j++;
      await sleep(delay);
      loadText(jumble("", _len), "target");
    }
    return 0;
  }

  async function removeCharacters(_output){
    await sleep(_output.length * delay + 4500)
    for(let i = _output.length; i >= 0; i--){
      html = _output.substring(0, i);
      html += "<span id='blinker'>█</span>";
      document.getElementById("target").innerHTML = html;
      await sleep(delay/3);
    }
  }

  async function createText (_output, _len){
      await sleep(loops * delay);
      for(let i = 1; i <= _len; i++){
        if(_output.substring(i,i+4) == "<br/>"){
          await sleep(500);
          loadText(jumble(_output.substring(0, i+4), _len), "target")
          i = i + 4;
        }else{
          loadText(jumble(_output.substring(0, i), _len), "target")
        }
        
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
  export default {
    name: 'FroststridersMain', 
    data: () => ({ isVisible: false }),
    components: {
      Box: posed.div({
        visible: { opacity: 1 },
        hidden: { opacity: 0 }
      })
    },
    mounted(){
      const stringToOutput = "TLAS.INIT()...<br/>FROSTSTRIDER_UI_LOAD()...<br/>COMPLETE";
      intro(stringToOutput.length);
      createText(stringToOutput, stringToOutput.length);
      // setTimeout(() => {
      //   this.isVisible = !this.isVisible;
      // }, ((delay * loops) + (stringToOutput.length * delay) + 2000));
    },
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url("https://fonts.googleapis.com/css?family=Unica+One");
.Froststriders_Cover * {
  color: #fceff9 !important;
  font-family: "Unica One", monospace !important;
}

.borders{
  width:30vw;
  height:20vh;
}
.borders:nth-of-type(1){
  position:fixed;
  top:5vh;
  left:5vw;
  border-top:3px solid #fceff9;
  border-left:3px solid #fceff9;
}
.borders:nth-of-type(2){
  position:fixed;
  top:5vh;
  right:5vw;
  border-top:3px solid #fceff9;
  border-right:3px solid #fceff9;
}
.borders:nth-of-type(3){
  position:fixed;
  bottom:5vh;
  left:5vw;
  border-bottom:3px solid #fceff9;
  border-left:3px solid #fceff9;
}
.borders:nth-of-type(4){
  position:fixed;
  bottom:5vh;
  right:5vw;
  border-bottom:3px solid #fceff9;
  border-right:3px solid #fceff9;
}


.Froststriders_Cover{
  position:fixed;
  top:0px;
  left:0px;
  width:100%;
  height:100vh;
  background:#101110;
  z-index:20000000;
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
