<template lang="pug">
footer.footer
    .container
        ul.footer__list
            li.footer__list-item
                n-link.footer__list-logo(to="/")
                        svg.footer__list-logo
                            use(href="@/assets/images/logo.svg#icon-untitled")
                ul.footer__list-copyright
                    li.footer__list-text © Все права защищены
                    li.footer__list-text Политика конфиденциальности
                    li.footer__list-text Публичная оферта
                    

            li.footer__list-nav
                ul.footer__menu 
                    li.footer__menu-item(v-for="item in items" :key="item.id") 
                        n-link(:to="item.route" exact active-class="active") {{ item.deafault }}
                        ul.footer__menu-sub
                            li.footer__menu-cloth(v-for="sub in item.submenu") 
                                n-link(to="/") {{ sub.text }}
            li.footer__list-info
                ul.footer__list-contacts
                    li.footer__list-number
                        a(href="tel:+380 000000000") +380 000000000
                    li.footer__list-mail
                        a(href="mailto:hello@womazing.com") hello@womazing.com
                ul.footer__list-socials
                    .footer__list-block
                        a(href="")
                            li.footer__list-instagram
                                svg(style="width:22px; height:22px")
                                    use(href="@/assets/images/socials.svg#icon-instagram-1-1")
                        a(href="")
                            li.footer__list-facebook
                                svg(style="width:21px; height:21px")
                                    use(href="@/assets/images/socials.svg#icon-facebook-1-1")
                        a(href="")
                            li.footer__list-twitter
                                svg(style="width:23px; height:23px")
                                    use(href="@/assets/images/socials.svg#icon-twitter-1-1")
                img.footer__list-card(src="@/assets/images/visa-mastercard 1.png")
               


    
</template>

<script>
    export default {
        data() {
            return {
                items:[
                    {
                        id:0,
                        deafault:"Главная",
                        route:"/",
                    },
                    {
                        id:1,
                        deafault:"Магазин",
                        route:"shop",
                        submenu:[
                            {
                                text:"Пальто",
                            },
                            {
                                text:"Свитшоты",
                            },
                            {
                                text:"Кардиганы",
                            },
                            {
                                text:"Толстовки",
                            },
                        ]
                    },
                    {
                        id:2,
                        deafault:"О бренде",
                        route:"about",
                    },
                    {
                        id:3,
                        deafault:"Контакты",
                        route:"contacts",
                    }
                ]
            }
        },
       
            
        
    }
</script>

<style lang="scss" scoped>
.active{
    color: #6E9C9F;
    font-weight: 700;
}

.footer{
    background: #F1EADC;
    padding: 101px;
   
    &__list{
        display: flex;
        
        &-block{
            display: flex;
            gap: 12px;
            float: right;

        }
        &-card{
            float: right;
            margin-top: 30px;
        }
        &-logo{
        width: 139px;
        height: 25px;
        }
        &-copyright{
            margin-top: 70px;
            font-weight: 400;
            font-size: 13px;
            line-height: 140%;
            letter-spacing: 0.02em;
            color: #000000;
            

        }
        &-text+&-text{
                margin-top: 6px;
            }
        &-item{
            margin-right: 81px;
        }
        &-nav{
            margin-right: 259px;
        }
        &-info{
            font-weight: 400;
            font-size: 15px;
            line-height: 140%;
            letter-spacing: 0.02em;
            color: #000000;
            text-align: right;
            ul+ul{
                margin-top: 30px;
            }
        }
        &-number{
            margin-bottom: 9px;
        }
    

    }
    
    &__menu{
        display: flex;
        &-item{
            font-weight: 400;
            font-size: 15px;
            line-height: 140%;
            letter-spacing: 0.02em;
            color: #000000;
        }
        &-item +&-item{
            margin-left: 45px;
        }
        &-cloth+ &-cloth{
            margin-top: 10px;

        }
        &-sub{
            font-weight: 400;
            font-size: 13px;
            line-height: 140%;
            letter-spacing: 0.02em;
            color: #000000;
            margin-top: 39px;
        }
    }
}

</style>