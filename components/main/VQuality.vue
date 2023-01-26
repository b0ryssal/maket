<template lang="pug">
section.quality
    h2.quality__title Что для нас важно
    ul.quality__list
        li.quality__list-item(v-for="block in blocks" :key="block.id")
            img.quality__list-image(:src="block.image")
            h3.quality__list-label {{ block.title }}
            p.quality__list-text {{ block.text }}
</template>

<script>
    export default {
        data() {
            return {
               blocks:[
                {
                    id:0,
                    image:require("@/assets/images/quality 1.svg"),
                    title:"Качество",
                    text:"Наши профессионалы работают на лучшем оборудовании для пошива одежды беспрецедентного качества",
                },
                {
                    id:1,
                    image:require("@/assets/images/Vector.svg"),
                    title:"Скорость",
                    text:"Благодаря отлаженной системе в Womazing мы можем отшивать до 20-ти единиц продукции в наших собственных цехах",
                },
                {
                    id:2,
                    image:require("@/assets/images/hand 1.svg"),
                    title:"Ответственность",
                    text:"Мы заботимся о людях и планете. Безотходное производство и комфортные условия труда - все это Womazing",
                },
               ]
            }
        },
        
    }
</script>

<style lang="scss" scoped>
.quality{
    padding: 130px 0 0 0;
    &__list{
        display: flex;
        gap: 30px;
    
        &-image{
            width: 61px;
            height: 61px;
            margin-bottom: 37px;
        }
        &-text{
            font-size: 17px;
            line-height: 140%;
            letter-spacing: 0.02em;
            color: #000000;
            margin-right: 45px;
           
        
        }
        &-label{
            font-size: 25px;
            line-height: 140%;
            letter-spacing: 0.02em;
            color: #000000;
            margin-bottom: 24px;
        }
    }
    &__title{
        font-weight: 500;
        font-size: 40px;
        line-height: 110%;
        letter-spacing: 0.02em;
        color: #000000;
        margin-bottom: 92px;
        

    }
}

</style>