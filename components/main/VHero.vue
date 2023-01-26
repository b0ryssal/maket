<template lang="pug">
section.hero
    ul.hero__new
        li
            h1.hero__new-title  Новые поступления в этом сезоне
        li.hero__new-text Утонченные сочетания и бархатные оттенки - вот то, что вы искали в этом сезоне. Время исследовать. 
        li.hero__new-item
            n-link(to="/shop").hero__new-button Открыть магазин
    .hero__images
        img(src="@/assets/images/main.png")
    .hero__poster


   
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
.hero{
    display: flex;
        gap: 151px;
        
       
        
    &__images{
        position: relative;
        z-index: 3;
        top: 41px;
        &::after{
            content: url("@/assets/images/secound.png");
            position: absolute;
            width: 197px;
            height: 197px;
            right: -105px;
            top: 110px;

        }
        &::before{
            content: url("@/assets/images/third.png");
            position: absolute;
            width: 197px;
            height: 197px;
            left: -130px;
            top: 388px;

        }
    }
    
    position: relative;
   
    
   
   
    &__new{
        
        padding-top: 186px;
        padding-bottom: 190px;
        &-title{
            
            font-size: 55px;
            line-height: 110%;
            font-weight: 500;
            letter-spacing: 0.02em;
            color: #000000;
            margin-bottom: 45px;
        }
        &-text{
            font-weight: 400;
            font-size: 20px;
            line-height: 140%;
            text-align: right;
            letter-spacing: 0.02em;
            color: #000000;
            margin-bottom: 52px;
            width: 385px;

        }
        &-item{
            display: flex;
            margin-left: 90px;
            &::before{
                content: url("@/assets/images/Vector 1.svg");
                display: block;
                padding: 19.5px 27px;
                background: rgba(110, 156, 159, 0.1);
            }
            
        }
        &-button{
            font-family: 'Raleway', sans-serif;
            background: #6E9C9F;
            padding: 22px 50px;
            font-weight: 400;
            font-size: 17px;
            line-height: 138.9%;
            display: flex;
            align-items: center;
           
           
            letter-spacing: 0.02em;
            color: #FFFFFF;
            transition: all 0.5s ease;
            &:hover{
                background: #509498;
            }
           
            
           

        }
        
       
    }
    &__poster{
       
        width: 705px;
        height: 826px;
        position: absolute;
        left: 650px;
        top: -80px;

        

        background: #F1EADC;
    }
}

</style>