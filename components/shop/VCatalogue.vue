<template lang="pug">
section.catalogue
    button.catalogue__filter(type="button"  @click="ShowShirt(button)" v-for="(button) in buttons") {{ button.name }}
       
       
    ul.catalogue__list
                li.catalogue__list-item(v-for="card in filteredCards" :key="card.id")
                    n-link.catalogue__list-base(to="")
                        img(:src="card.image")
                        .catalogue__list-info
                            h3.catalogue__list-title {{ card.title }}
                            .catalogue__list-price
                                p.catalogue__list-oldprice(:style="card.style") {{ card.oldprice }}
                                p.catalogue__list-number ${{ card.price }}
        
</template>
    <script>    
    
        export default {
            computed: {
              filteredCards() {
                    if(this.sortedCards.length){
                        return this.sortedCards
                    }else{
                        return this.cards
                    }
                }
            },
        
           
                
            
            methods: {
                
               
                ShowShirt(button) {
                    this.selected=button.name;
                    this.sortedCards=[];
                    
                    let vm=this
                    this.cards.map((el)=>{
                        if(el.type===button.name){
                            vm.sortedCards.push(el);
                        }
                        
                    })
                   
                  
                    
    
                }                   
            },
            mounted () {
                let panels = document.getElementsByClassName("catalogue__filter");
                    let actives = document.getElementsByClassName("opened");
                    for ( let i = 0; panels.length > i; i++) {
                    panels[i].onclick = function() {
                        const currentActive = actives[0];
                        if (currentActive)
                            currentActive.classList.remove("opened");
                        if (currentActive !== this)
                            this.classList.add("opened");
                        if(currentActive==this)
                            this.classList.add("opened");
                    }
                };
            },
            data() {
                return {
                    sortedCards:[],
                    selected:'',
                    buttons:[
                        {
                            id:0,
                            name:"Все",
                          
    
                        },
                        {
                            id:1,
                            name:"Футболки",
                            
    
                        },
                        {
                            id:2,
                            name:"Купальники",
                           
    
    
                        },
                        {
                            id:3,
                            name:"Свитшоты",
                        }
                    ],
                    cards:[
                    {
                        id:0,
                        image:require("@/assets/images/card1.png"),
                        title:"Футболка USA",
                        oldprice:"$229",
                        style:"margin-right:10px;",
                        type:"Футболки",
                      
                      
                       
                    
                        price:129,
                    },
                    {
                        id:1,
                        image:require("@/assets/images/card2.png"),
                        title:"Купальник Glow",
                        type:"Купальники",
                        price:129,
                      
                        
                       
                    },
                    {
                        id:2,
                        image:require("@/assets/images/card3.png"),
                        title:"Свитшот Sweet Shot",
                        type:"Свитшоты",
                        
                        
                     
                        price:129,
                       
                       
                    },
                    {
                        id:3,
                        image:require("@/assets/images/card1.png"),
                        title:"Футболка USA",
                        oldprice:"$229",
                        style:"margin-right:10px;",
                        type:"Футболки",
                       
                        
                       
                    
                        price:129,
                    },
                    {
                        id:4,
                        image:require("@/assets/images/card2.png"),
                        title:"Купальник Glow",
                        type:"Купальники",
                        
                       
                       
                      
                        price:129,
                    },
                    {
                        id:5,
                        image:require("@/assets/images/card3.png"),
                        title:"Свитшот Sweet Shot",
                        type:"Свитшоты",
                       
                     
                        price:129,
                    },
                    {
                        id:6,
                        image:require("@/assets/images/card1.png"),
                        title:"Футболка USA",
                        oldprice:"$229",
                        style:"margin-right:10px;",
                        type:"Футболки",
                      
                      
                       
                    
                        price:129,
                    },
                    {
                        id:7,
                        image:require("@/assets/images/card2.png"),
                        title:"Купальник Glow",
                        type:"Купальники",
                        price:129,
                      
                        
                       
                    },
                    {
                        id:8,
                        image:require("@/assets/images/card3.png"),
                        title:"Свитшот Sweet Shot",
                        type:"Свитшоты",
                        
                        
                     
                        price:129,
                       
                       
                    },
                   ]
                }
            },
            
            
        }
    </script>
    
    <style lang="scss" scoped>
       .opened{
        background-color: black;
        color: #FFFFFF;
    }
    
    
    
    .catalogue{
        &__filter{
            padding: 19px 65px;
            border: 1px solid #000000;
            margin: 50px 0;
            cursor: pointer;
        
        }
        &__filter+&__filter{
            margin-left: 10px;
    
        }
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
            flex-wrap: wrap;
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
                margin-bottom: 20px;
                
               
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