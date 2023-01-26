<template lang="pug">
section.collections
    h2.collections__title Новая коллекция
    ul.collections__list
            li.collections__list-item(v-for="card in cards" :key="card.id")
                n-link.collections__list-base(to="")
                    img(:src="card.image")
                    .collections__list-info
                        h3.collections__list-title {{ card.title }}
                        .collections__list-price
                            p.collections__list-oldprice(:style="card.style") {{ card.oldprice }}
                            p.collections__list-number ${{ card.price }}
    n-link(to="/shop").collections__button Открыть магазин

   
</template>

<script>
    export default {
        data() {
            return {
               cards:[
                {
                    id:0,
                    image:require("@/assets/images/card1.png"),
                    title:"Футболка USA",
                    oldprice:"$229",
                    style:"margin-right:10px;",
                
                    price:129,
                },
                {
                    id:1,
                    image:require("@/assets/images/card2.png"),
                    title:"Купальник Glow",
                  
                    price:129,
                },
                {
                    id:2,
                    image:require("@/assets/images/card3.png"),
                    title:"Свитшот Sweet Shot",
                 
                    price:129,
                }
               ]
            }
        },
        
    }
</script>

<style lang="scss" scoped>
.collections{
    padding: 130px 0 0 0;
    &__button{
        font-weight: 400;
        font-size: 17px;
        line-height: 138.9%;
        text-align: center;
        letter-spacing: 0.02em;
        color: #6E9C9F;
        padding: 22px 50px;
        width: fit-content;
        display: block;
        margin: 0 auto;
        margin-top: 65px;
        transition: all 0.5s ease;
        
        border: 1px solid #6E9C9F;
        &:hover{
            background: #6E9C9F;
            color: #FFFFFF;
        }
    }
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
        gap: 30px;
        &-base{
            position: relative;
            &::before{
                    content: url("@/assets/images/Vector 2.svg");
                    position: absolute;
                    padding: 224px 159px;
                    background: rgba(110, 156, 159, 0.64); 
                    opacity: 0;
                    transition: all 0.5s ease;  
            }
            
            &:hover{
                &::before{
                    content: url("@/assets/images/Vector 2.svg");
                    position: absolute;
                    padding: 224px 159px;
                    background: rgba(110, 156, 159, 0.64); 
                    transition: all 0.5s ease; 
                    opacity: 1;
            }

            }
           
            
            
            
        }
       
       
        &-price{
            display: flex;
            justify-content: center;
            font-size: 15px;
            line-height: 140%;
            letter-spacing: 0.02em;
            font-weight: 500;
            
           
        }
        &-info{
            padding-top: 24px;
        }
        &-title{
            text-align: center;
            margin-bottom: 7px;
            font-size: 20px;
            line-height: 140%;
            letter-spacing: 0.02em;
            color: #000000;
            font-weight: 500;
        }

        &-oldprice{
            
            text-decoration-line: line-through;
            color: #9C9C9C;
        }
        &-number{
            color: #998E78;
        }
        
       
    }

}

</style>