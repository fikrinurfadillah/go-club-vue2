<template>
    <nav class="fixed">
        <!-- <label class="logo">DesignX</label> -->
        <img class="logo" v-bind:src="logoLink">
        <ul :class="navIsSelected ? 'show' : ''">
            <li><a class="active" href="#">Home</a></li>    
            <li @click="toggleDropdown1()">
                <a href="#">Partner with us<i class="fas fa-angle-down"></i></a>
                <ul v-if="dropdownIsSelected1" class="row dropdown">
                    <li class="col-md-3">
                        <a>Driver Partners</a>
                    </li>
                    <li class="col-md-3">
                        <a>Merchant Partners</a>
                    </li>
                </ul>
            </li>
            <li><a href="#">Career</a></li>
            <li @click="toggleDropdown2()">
                <a href="#">Company<i class="fas fa-angle-down"></i></a>
                <ul v-if="dropdownIsSelected2" class="row dropdown">
                    <li class="col-md-3">About</li>
                    <li class="col-md-3">Safety</li>
                    <li class="col-md-3">Sutainability</li>
                    <li class="col-md-3">Newsroom</li>
                </ul>
            </li>
            <li><a href="#">Products</a></li>
            <li><a href="#">Blog</a></li>
            <li><a href="#">Help</a></li>
            <li><i class="fas fa-language"></i><a href="#">EN</a></li>
        </ul>
        <label id="icon" @click="navSelected">
            <i :class="navIsSelected ? 'fas fa-times' : 'fas fa-bars'"></i>
        </label>    
    </nav>    
</template>

<script>
export default {
    data(){
        return {
            logoLink: 'https://lelogama.go-jek.com/service_icon_text/gojek-logo_normal.svg',
            navIsSelected: false,
            dropdownIsSelected1: false,
            dropdownIsSelected2: false
         }    
    },
    // computed: {
    //     navClasses() {

    //     }
    // },
    methods: {
        navSelected() {
            this.navIsSelected = !this.navIsSelected
        },
        // eslint-disable-next-line
        toggleDropdown1() {
            this.dropdownIsSelected1 = !this.dropdownIsSelected1
        },
        toggleDropdown2() {
            this.dropdownIsSelected2 = !this.dropdownIsSelected2
        }
    }
}
</script>
<style scoped>

* {
    padding: 0;
    margin: 0;
    list-style-type: none;
    text-decoration: none;
}

nav {
    height: 70px;
    width: 100%;
    background: white;
    justify-content: space-between;
    box-shadow: 0 2px 6px 0 rgb(0 0 0 / 20%);
}


.logo {   
    padding: 25px 100px;
    line-height: 80px;
}

.fixed {
  position:fixed;
  top:0;
  left:0;
  right:0;
  width:100%;
  z-index:99;
  background:white;
}

nav ul {
    float: right;
    margin-right: 20px;
    align-content: space-between;
}

nav li {
    display: inline-block;
    margin: 0 25px;
    line-height: 80px;
   
}

nav a {
    color: black;
    font-weight: 550;
    font-size: 18px;
}

a.active, a:hover {
    color: green;
    transition: .5s;
}

nav #icon {
    color: green;
    font-size: 30px;
    line-height: 80px;
    float: right;
    margin-right: 40px;
    cursor: pointer;
    display: none;
}

.dropdown {
    /* max-width: unset; */
    width: 100%;
    padding: 0 ;
    position: fixed;
    /* visibility: hidden; */
    /* opacity: 0; */
    background-color: #f7f7f7;
    top: 70px;
    left: 0;
    right: 0;
    list-style-type: none;
}

@media (max-width: 1048px) {
    .logo{
        padding-left: 60px;
    }
    nav ul {
        margin-right: 20px;
    }
    nav a {
        font-size: 17px;
    }
}


@media (max-width: 909px) {
    nav #icon {
        display: block;
    }
    nav ul {
        position: fixed;
        width: 100%;
        height: 100vh;
        background: #2f3640;
        top: 80px;
        left: -100%;
        text-align: center;
        transition: all .5s;
    }
    nav li {
        display: block;
        margin: 50px 0;
        line-height: 30px;
    }
    nav a {
        font-size: 20px;
    }
    a.active, a:hover {
        border: none;
        color: #3498db;
    }
    nav ul.show{
        left: 0;

    }
}
</style>