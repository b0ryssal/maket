<template lang="pug">

header.header(:class="{'popup-open': $store.state.popup.showPopup ,'header__fixed': scrollPosition>50}" )
    .container
        n-link.header__logo(to="/")
            svg.header__logo
                use(href="@/assets/images/logo.svg#icon-untitled")
        ul.header__menu 
            li.header__menu-item(v-for="item in items" :key="item.id") 
                n-link(:to="item.route" exact active-class="active") {{ item.deafault }}
        ul.header__feedback
            li.header__feedback-number
                button(type="button" @click="toggleDropdown")
                    svg.header__feedback-svg
                        use(href="@/assets/images/tel.svg#icon-telephone")

                p.header__feedback-phone +380 000000000
            li.header__feedback-cart
                n-link(to="")
                    svg.header__feedback-bag
                        use(href="@/assets/images/bag.svg#icon-shopping-bags")
    
</template>

<script>
    export default {
        
        data() {
            
            return {
                scrollPosition: null,
              
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
        methods:{
            toggleDropdown(){
                // document.body.dataset.position = window.scrollY;
                this.$store.dispatch("popup/toggle");
                // document.body.style.top= -window.scrollY+'px'
                // document.body.style.position = 'fixed';
                // document.body.style.margin = '0 auto';
                // document.body.style.width = '100vw';
                
               
                
                                
                
            },
            scrollHeader(){
                this.scrollPosition=window.scrollY;
                
            },

            
            
        },
        
        mounted(){
            window.addEventListener('scroll', this.scrollHeader);

            
           


        },

        

       
            
        
        
    }
</script>

<style lang="scss" scoped>
@keyframes header {
    0%{
        top: -80px;
    }
    100%{
        top: 0;   
    }
    
}

.active{
    color: #6E9C9F;
    font-weight: 700;
}
.container{
    display: flex;
    align-items: center;

}

.header{
   
    padding: 50px 0 0 0;
    width: 100%;
    
    font-weight: 400;
    font-size: 15px;
    line-height: 140%;
    letter-spacing: 0.02em;
    color: #000000;
    position: relative;
    z-index: 4;
    
    background: transparent;
    
    &__fixed{
    padding: 37px 0;
    box-shadow: 0px 4px 15px rgba(0, 0, 0, 0.05);
    background: #FFFFFF;
    position: fixed;
    animation-name: header;
    animation-duration: 1s;



}
    
   

    &__logo{
        width: 139px;
        height: 25px;
        margin-right: 146px;
    }
    &__menu{
        display: flex;
        align-items: center;
        
        &-item+&-item{
            margin-left: 45px;
        }
        margin-right: 170px;
    }
    &__feedback{
        display: flex;
        gap: 76px;
       
        align-items: center;
        &-number{
            display: flex;
            align-items: center;
            button{
                cursor: pointer;
            }
          

            
        }
        &-svg{
            width: 27px;
            height: 27px;
            margin-right: 4px;
            display: block;
            fill: #6E9C9F;
            transition: all 0.5s ease;
            &:hover{
                background: #6E9C9F;
                fill: #FFFFFF;
            }
        }
       
        &-bag{
            width: 24px;
            height: 24px;
        }
     
        
    }

}


</style>