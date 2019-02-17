<template>
    <div class="FroststridersContent">
        <div class="Hero_Section">
            <div class="Hero">
            </div>
        </div>
        <div class="Content_Display">
            <h2>TLAS</h2>
            <h3>Threat</h3>
            <h3>Level</h3>
            <h3>Analysis</h3>
            <h3>System</h3>
            
        </div>
        <div class="Powered_By">
            <div class="Vast_Pinnacle_Logo_Container">
                <h2 class="Vast_Pinnacle_Text">
                    <span class="heavy">V</span>AST
                    <br/>PINNACLE
                    <br/>GAMES</h2>
                    <div class="Vast_Pinnacle_Logo"  alt="Vast Pinnacle Logo"/>
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
    /* https://coolors.co/101110-4c4c47-fe5f55-023a7f-bec4c4 */
    .Hero_Section{
        width:100vw;
        height:calc(80vh - 60px);
        padding:30px 0px;
    }
    .Hero{
        height:400px;
        width:400px;
        margin:0 auto;
        background-image:url(../assets/Ice-Shelf-Cut.jpg);
        background-size:contain;
    }

    .Content_Display{
        width:100vw;
        height:auto;
        padding:30px 0px;
        background:#4c4c47;
    }

    .Powered_By{
        width:100vw;
        background:white;
        padding:30px 0px;
    }
    .Vast_Pinnacle_Logo_Container{
        width:100vw;
        height:auto;

        position:relative;
        border-radius:5px;
        
        left:50%;
        transform:translateX(-50%);

        display:block;
        clear:both;

    }
    .Vast_Pinnacle_Logo{
        width:100%;
        max-width:450px;
        margin:0 auto;
        padding-top:50%;
        background-repeat:no-repeat;
        transform:translateY(5px);
        background-size:80%;
        background-position:center top;
        background-image:url(../assets/VastPinnacle.svg);
    }
    @media screen and (min-width:450px){
        .Vast_Pinnacle_Logo{
            padding-top:225px;
        }
    }
    .Vast_Pinnacle_Text{
        text-align:center;
        letter-spacing:3px;
        color:#a0a5a5 !important;
        font-weight:400 !important;
        background:white;
    }

    .heavy{
        font-weight:700;
        color:#a0a5a5 !important;
    }
</style>
