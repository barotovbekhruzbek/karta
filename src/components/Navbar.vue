<template>
    <header :class="{ scrolled: isScrolled }">
        <div class="container">
            <nav class="navbar" >
                <h2 class="logo">Logo</h2>

                <div v-if="isMobile" class="burger" :class="{ active: isOpen}" @click="isOpen = !isOpen">
                    <span v-if="!isOpen">&#9776;</span>
                    <span v-if="isOpen">&#10008;</span>
                </div>

                <ul class="menu" v-if="!isMobile">
                    <li v-for="list in menuList" :key="list.text">
                        <a :href="list.link" class="link">{{ list.text }}</a>
                    </li>
                </ul>

                <ul class="mobile-menu" :class="{active: isOpen}" v-if="isMobile">
                    <li v-for="item in menuList" :key="item.text">
                        <a :href="item.link" class="link">{{ item.text }}</a>
                    </li>
                </ul>
            </nav>
        </div>
    </header>
</template>


<script>
export default {
    data() {
        return {
            isMobile: false,
            isOpen: false,
            isScrolled: false,
            menuList: [
              {
                text: 'Home',
                link: 'https://google.com'
              },
              {
                text: 'About',
                link: '#'
              },
              {
                text: 'Blog',
                link: '#'
              },
              {
                text: 'Contact',
                link: '#'
              }

            ]
        }
    },
    methods: {
       checkScreen(){
           const windowWidth = window.innerWidth
           if(windowWidth <= 600) {
               this.isMobile = true
               return
           }
           this.isMobile = false
           this.isOpen = false
       } 
    },
    mounted() {
        this.checkScreen()
        window.addEventListener("resize", this.checkScreen)
        window.addEventListener("scroll", () => {
            if(pageYOffset > 0){
                this.isScrolled = true
                return
            }
             this.isScrolled = false
        })
    }
}
</script>


 
<style scoped>
    header{
        background: #000;
        padding: 35px 0;
        position: absolute;
        left: 0;
        top: 0;
        width: 100%;
        transition: 0.7s;
    }

    header.scrolled{
        padding: 25px 0;
        background: #a9a9a9;
        color: #000 !important;
        position: fixed;

    }

    header.scrolled a{
        color: #000 !important;
    }



    .burger{
        width: 30px;
        height: 30px;
        border: 1px solid #ececec;
        border-radius: 5px;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 20px;
        position: relative;
        z-index: 999;
    }
    .burger.active{
        color: aqua;
        border-color: aqua;
    }
     
    .navbar{
        display: flex;
        justify-content:space-between;
        align-items: center;
    }

    .logo{
        font-size: 50px;
        position: relative;
        z-index: 999;
    }

    .menu{
       display: flex;
       gap : 30px ;
       align-items: center; 
    }

    .menu li a{
        font-size: 20px;
    }
    .menu li a:hover{
        color: aqua;
    }

    .mobile-menu{
        position: fixed;
        left: 0;
        top: 0;
        width: 100%;
        height: 100vh;
        background:#000;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        opacity: 0;
        pointer-events: none;
        transition: 0.7s;
    }

    .mobile-menu.active{
        opacity: 1;
        pointer-events: none;
    }

    .mobile-menu .link{
        font-size: 25px;
        padding: 20px;
    }

    .mobile-menu li a:hover{
        color: aqua;
    }


</style>