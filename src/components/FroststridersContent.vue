<template>
    <div class="FroststridersContent">
        <div class="Hero_Section">
            Froststriders
        </div>
        <div class="Content_Display">
            Content
        </div>
        <div class="Powered_By">
            <div class="Vast_Pinnacle_Logo_Container">
                <h2 class="Vast_Pinnacle_Text">VAST<br/>PINNACLE</h2>
                <img class="Vast_Pinnacle_Logo" src="../assets/VastPinnacle.svg" alt="Vast Pinnacle Logo"/>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'FroststridersContent'
}
</script>

<style scoped>
    /* https://coolors.co/101110-2f2d2e-011936-bec4c4-d1a58a */
    .Hero_Section{
        width:100vw;
        height:80vh;
        background:#011936;
    }

    .Content_Display{
        width:100vw;
        height:auto;
        min-height:400px;
    }

    .Powered_By{
        width:100vw;
        background:#bec4c4;
        padding:30px 0;
    }
    .Vast_Pinnacle_Logo_Container{
        background:white;
        width:30vw;
        height:auto;
        border:5px solid white;
        width:30vw;
        height:auto;
        

        position:relative;
        border-radius:30px;
        
        left:50%;
        transform:translateX(-50%);

        display:block;
        clear:both;

    }
    .Vast_Pinnacle_Logo{
        width:100%;
        border-radius:30px;
        transform:translateY(5px);
    }
    .Vast_Pinnacle_Text{
        text-align:center;
        letter-spacing:3px;
        color:#a0a5a5;
    }
</style>
