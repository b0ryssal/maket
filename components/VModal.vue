<template lang="pug">
.modal(:class="{'popup-close': !$store.state.popup.showPopup}")
    .modal__block

        img(src="@/assets/images/Close.svg" @click="toggleDropdown")
        h2.modal__block-title Заказать обратный звонок
        ul.modal__block-list
            li.modal__block-item(v-for="input in inputs" :key="input.id")
                input(:type="input.type", :placeholder="input.placeholder")
        button.modal__block-button(type="button") Заказать звонок
            
   
</template>

<script>
    export default {
        data() {
            return {
                
                inputs:[
                    {
                        id:0,
                        placeholder:"Имя",
                        type:"text"
                    },
                    {
                        id:1,
                        placeholder:"E-mail",
                        type:"email"
                    },
                    {
                        id:2,
                        placeholder:"Телефон",
                        type:"tel"
                    },
                ]
               
            }
        },
        methods:{
            toggleDropdown(){
                this.$store.dispatch("popup/toggle");
                // document.body.style.position = '';
                
                
                // window.scroll({top:document.body.dataset});
                
                
            },
           
        },
        

        
    }
</script>

<style lang="scss" scoped>

.modal{
  
    width: 100%;
    height: 100%;
    position: fixed;
    left: 0;
    top: 0;
    z-index: 5;
    display: flex;
    align-items: center;
    justify-content: center;
    
    transform: translateY(0%);
    transition: all 1s ease;
    &::before{
        content: "";
        position: fixed;
        background: rgba(110, 156, 159, 0.95);
        width: 100%;
        height: 100%;
        transition: all 1s ease;
        transition-delay: 0.8s;
    }
    
   
  
    
    
    
    
    &__block{
        background: #FFFFFF;
        padding: 70px;
        position: relative;
        
       
            
        &-button{
            padding: 22px 108px;
            background: #6E9C9F;
            border: 0;
            font-weight: 400;
            font-size: 17px;
            line-height: 138.9%;
            text-align: center;
            letter-spacing: 0.02em;
            color: #FFFFFF;
            margin-top: 35px;
            cursor: pointer;
            
            transition: all 0.5s ease;
            &:hover{
                background: #509498;
                
            }

        }
        img{
            display: block;
            position: absolute;
            top: 32px;
            left: 445px;
            cursor: pointer;
        }
        &-title{
            margin-bottom: 35px;
            font-weight: 500;
            font-size: 25px;
            line-height: 140%;
            letter-spacing: 0.02em;
            color: #000000;
            padding: 0 10px;
        }
        &-item+&-item{
            margin-top: 35px;
        }
        &-item{
            input{
                width: 100%;
                border: 0;
                border-bottom: 1px solid #000000;
                padding-bottom: 16px;
                font-weight: 500;
                font-size: 17px;
                line-height: 140%;
                letter-spacing: 0.02em;
                color: #868686;
                &:focus{
                    outline: 0;
                }

            }
           
        }
       
        
       

    }
}
.popup-close{
    transform: translateY(-200%);
   
    transition: all 2s ease;
    &::before{
        content: "";
        position: fixed;
       
        width: 100%;
        height: 100%;
        transition: all 0s ease;
        transition-delay: 0s;
        background: none;
    }
        

   
    
   
    
    

   
    
    
}



</style>