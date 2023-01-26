<template lang="pug">
section.team
    h2.team__title Команда мечты Womazing
    ul.team__list 
        li.team__list-item 
            img.team__list-image(src="@/assets/images/team.png")
        li.team__list-item 
            h3.team__list-title Для каждой
            p.team__list-text Каждая девушка уникальна. Однако, мы схожи в миллионе мелочей. Womazing ищет эти мелочи и создает прекрасные вещи, которые выгодно подчеркивают достоинства каждой девушки.
            n-link.team__list-link(to="about") Подробнее о бренде 

    
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
.team{
    padding: 130px 0;
    &__title{
        margin-bottom: 92px;
        font-weight: 500;
        font-size: 40px;
        line-height: 110%;
        letter-spacing: 0.02em;
        color: #000000;

    }
    &__list{
        display: flex;
        &-image{
            width: 729px;
            height: 487.42px;
        }
        &-item+&-item{
            padding: 78px 0 78px 124px;

        }
        &-title{
            font-weight: 500;
            font-size: 25px;
            line-height: 140%;
            letter-spacing: 0.02em;
            color: #000000;
            margin-bottom: 28px;            
        }
        &-text{
            font-weight: 500;
            font-size: 17px;
            line-height: 140%;
            letter-spacing: 0.02em;
            color: #000000;
            margin-bottom: 28px;

        }
        &-link{
            font-weight: 500;
            font-size: 17px;
            line-height: 140%;
            letter-spacing: 0.02em;
            color: #6E9C9F;
            padding-bottom: 5px; 
            transition: all 0.5s ease;
            border-bottom: 1px solid transparent;
            &:hover{
                border-bottom: 1px solid #CEDEDF;
            }

        }
    }
    
}

</style>