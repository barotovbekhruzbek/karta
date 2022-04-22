<template>
    <div class="wrapper">
        <div class="btns">
            <button
             v-for="(country, idx) in countries"
              :key="country.name"
              :class="{ active: activeBtn === idx }"
              @click="activeBtn = idx"

              >
                    {{ country.name }}
            </button>
          
        </div>
        <div class="block">
            <div class="left">
                <div class="flag">
                    <img :src="countries[activeBtn].flag" alt="flag">
                </div>
                <div class="box">
                    <h3>Address</h3>
                   <a :href="countries[activeBtn].adress.link" target="_blank">{{ countries[activeBtn].adress.text }}</a>
                </div>

                  <div class="box">
                    <h3>Phone</h3>
                   <a :href="countries[activeBtn].phone.link">{{ countries[activeBtn].phone.text  }}</a>
                </div>


                    <div class="box">
                    <h3>Email</h3>
                   <a :href="countries[activeBtn].email">{{ countries[activeBtn].email }}</a>
                </div>


                    <div class="box">
                    <h3>Website</h3>
                   <a :href="countries[activeBtn].website.link" target="_blank">{{ countries[activeBtn].website.text }}</a>
                </div>


            </div>


            <div class="right" v-html="countries[activeBtn].map">
                    
            </div>

        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            activeBtn:0,
            countries : [
                {
                    name: 'Uzbekiston',
                    adress: {
                        text: 'Tashkent, Nmadir City,Uzbekistan',
                        link: 'https://goo.gl/maps/jjv9XZt63DLtsSao9'
                    },
                    phone: {
                        text: '+998 (33) 123 45 67',
                        link: '+998331234567'
                    },
                    email: 'uzb@example.com',
                    website: {
                        text :'hoshim-hacker.io',
                        link: 'https://google.com'
                    },
                    flag: require('@/assets/flas/flagu.png'),
                    map: `<iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2996.6418217259834!2d69.24629541580974!3d41.31665497927067!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x38ae8b40d847941d%3A0x5765a18b352df71e!2sTashkent%20City%20Park!5e0!3m2!1sru!2s!4v1650372600532!5m2!1sru!2s" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>`
                },

                        {
                    name: 'Avganiston',
                    adress: {
                        text: 'Kandagar, Nmadir City, Afganistan',
                        link: 'https://goo.gl/maps/KmihWgUsdcpj8oCM9'
                    },
                    phone: {
                        text: '+011 (33) 123 45 67',
                        link: '+01331234567'
                    },
                    email: 'afgan@example.com',
                    website: {
                        text :'gani-hacker.io',
                        link: 'https://google.com'
                    },
                    flag: require('@/assets/flas/flaga.jpg'),
                    map: `<iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d6785928.561590737!2d63.21309852180609!3d33.85250637835991!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x38d16eb6f8ff026d%3A0xf3b5460dbe96da78!2z0JDRhNCz0LDQvdC40YHRgtCw0L0!5e0!3m2!1sru!2s!4v1650372723943!5m2!1sru!2s"   allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>`
                },



                        {
                    name: 'Afrika',
                    adress: {
                        text: 'Zenbabe, Black City,Afrika',
                        link: 'https://goo.gl/maps/bR5WjGGRDFDmgarc7'
                    },
                    phone: {
                        text: '+998 (33) 123 45 67',
                        link: '+998331234567'
                    },
                    email: 'usa@example.com',
                    website: {
                        text :'black-hacker.io',
                        link: 'https://google.com'
                    },
                    flag: require('@/assets/flas/flagaf.png'),
                    map: `<iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d32661585.375405382!2d5.196516862750441!3d2.149883919184999!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x10a06c0a948cf5d5%3A0x108270c99e90f0b3!2z0JDRhNGA0LjQutCw!5e0!3m2!1sru!2s!4v1650372804740!5m2!1sru!2s"  allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>`
                },



                    {
                    name: 'india',
                    adress: {
                        text: 'Dehli, Black City,Dehli',
                        link: 'https://goo.gl/maps/HDDXuWVZ1C959JnAA'
                    },
                    phone: {
                        text: '+998 (33) 123 45 67',
                        link: '+998331234567'
                    },
                    email: 'india@example.com',
                    website: {
                        text :'chopra-hacker.io',
                        link: 'https://google.com'
                    },
                    flag: require('@/assets/flas/flagi.png'),
                    map: `<iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d15282198.718343014!2d73.73011708874675!3d20.750569284681987!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x30635ff06b92b791%3A0xd78c4fa1854213a6!2z0JjQvdC00LjRjw!5e0!3m2!1sru!2s!4v1650372831517!5m2!1sru!2s" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>`
                },
                    
                    
                    {
                    name: 'New Zeland',
                    adress: {
                        text: 'Good Place, Black City,New Zelland',
                        link: 'https://goo.gl/maps/XdAYLTXMbSUbe3Zo9'
                    },
                    phone: {
                        text: '+998 (33) 123 45 67',
                        link: '+998331234567'
                    },
                    email: 'zelland@example.com',
                    website: {
                        text :'newzelland-hacker.io',
                        link: 'https://google.com'
                    },
                    flag: require('@/assets/flas/flagz.png'),
                    map: `<iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d12412833.039330183!2d166.0216207517182!3d-40.57522942586833!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x6d2c200e17779687%3A0xb1d618e2756a4733!2z0J3QvtCy0LDRjyDQl9C10LvQsNC90LTQuNGP!5e0!3m2!1sru!2s!4v1650372869195!5m2!1sru!2s" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>`
                }

            ]
        }
    },
}
</script>

<style scoped lang="scss">
    .wrapper{
        margin-top: 100px;

    }
    .btns{
        display: flex;
        justify-content: center;
        gap: 30px;
    }

  .btns button{
      padding: 10px 30px;
      font-size: 15px;
      font-weight: 600;
      color: #fff;
      background:transparent ;
      letter-spacing: 2px;
      border: 2px solid #fff;
      border-radius: 50px;
    }
    .btns button.active{
        color: aqua;
        border-color: aqua;
    }

    .block{
        display: flex;
        justify-content: space-between;
        margin-top: 100px;

    }
    .left{
        padding-right: 50px;
        width: 50%;

    }
    .box{
        margin-bottom: 30px;

    }
    .flag{
        min-width: 300px;
        height: 100px;
        /* background: rgba(255, 255, 255, 0.1); */
        margin-bottom: 30px;
    }
    .flag img{
        height: 100%;

    }
    .box h3{
        font-size: 20px;
       margin-bottom: 10px;
    }
    .box a{
        font-size: 25px;
        color: #fff;
        &:hover{
            color: aqua;

        }
    }
    .right{
        width: 50%;
        // height: 400px;
        background: rgba(255,255,255,0.1);   
    
    }
    .right iframe {
        width: 100%;
        height: 100%;
        border: none;
    }
</style>