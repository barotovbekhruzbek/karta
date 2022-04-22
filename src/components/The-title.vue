<template>
    <div class="site-title">
        <h2>This title</h2>
        <h4>This is subtitle</h4>
        <div class="line"></div>
    </div>
</template>


<script>
export default {
    
}
</script>



<style scoped>
    .site-title{
        text-align: center;
        color: #cecece;
    }

    h2{
      font-size: 30px;  
    }

    h4{
        color: aqua;
        font-family:'Courier New', Courier, monospace;
        margin-top: 20px;
    }

    .line{
        width: 100px;
        height: 2px;
        background: aqua;
        margin: 30px auto;
    }

</style>