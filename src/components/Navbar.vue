<template>
    <header class="main-header">
        <nav class="page-nav">
            <div class="main-nav">
                <ul class="navlinks main">
                    <li class="nav-item nav-link">
                        <router-link to="/">Home</router-link>
                    </li>
                    <li class="nav-item nav-link">
                        <router-link to="/shops">Shops</router-link>
                    </li>
                    <li class="nav-item nav-link">
                        <router-link to="/products">Products</router-link>
                    </li>
                    <li class="nav-item auth">
                        <a class="login">Login</a>
                    </li>
                </ul>
                <router-link to="/" class="logo">
                    <span>LOGO</span>
                </router-link>
                <ul class="navlinks main">
                    <li class="nav-item nav-link will-disappear">
                        <router-link to="/health-expert">Health Expert</router-link>
                    </li>
                    <li class="nav-item nav-link will-disappear">
                        <router-link to="/faq">FAQ</router-link>
                    </li>
                    <li class="nav-item nav-link will-disappear">
                        <router-link to="/contact">Contact Us</router-link>
                    </li>
                    <li class="nav-item search">
                        <input type="text" id="search" placeholder="Search baby item">
                        <span class="search-icon-main">
                            <i class="fas fa-search search-item"></i>
                        </span>
                    </li>
                    <li class="nav-item cart">
                        <router-link to="/cart">
                            <i class="fas fa-shopping-cart"></i>
                        </router-link>
                    </li>
                </ul>
            </div>
            <div class="responsive-nav">
                <router-link to="/" class="logo will-disappear">
                    <span>LOGO</span>
                </router-link>
                <ul class="responsive">
                    <li class="nav-item will-disappear">
                        <a class="login">Login</a>
                    </li>
                    <li class="nav-item cart will-disappear">
                        <router-link to="/cart">
                            <i class="fas fa-shopping-cart"></i>
                        </router-link>
                    </li>
                    <li class="nav-item search">
                        <input type="text" id="search-responsive" placeholder="Search baby item">
                        <span class="search-icon-res">
                            <i class="fas fa-search search-item"></i>
                        </span>
                    </li>
                </ul>
                <div class="hamburger">
                    <div class="line line1"></div>
                    <div class="line line2"></div>
                    <div class="line line3"></div>
                </div>
            </div>
        </nav>
    </header>
</template>

<script>
export default {
    mounted() {

        const navbar = document.querySelector('.page-nav'),
            hamburger = document.querySelector('.hamburger'),
            navlinks = document.querySelectorAll('.nav-link'),
            navItemsResponsive = document.querySelectorAll('.responsive-nav .will-disappear'),
            mainNavItems = document.querySelectorAll('.main-nav .will-disappear'),
            responsiveSearch = document.querySelector('.search-icon-res'),
            searchBoxMain = document.getElementById('search'),
            searchBoxResponsive = document.getElementById('search-responsive'),
            mainNavSearch = document.querySelector('.search-icon-main');

        hamburger.addEventListener('click', _ => {
            navbar.classList.toggle('active')
            document.body.classList.toggle('overlay')
        })

        navlinks.forEach(link => {
            link.addEventListener('click', _ => {
                if (navbar.classList.contains('active')) {
                    navbar.classList.remove('active')
                    document.body.classList.remove('overlay')
                }
            })
        })

        window.addEventListener('click', e => {
            const mainNav = document.querySelector('.page-nav');
            if (!mainNav.contains(e.target)) {
                navbar.classList.remove('active')
                document.body.classList.remove('overlay')
            }
        })

        responsiveSearch.addEventListener('click', _ => {
            navItemsResponsive.forEach(item => {
                item.classList.toggle('disappear')
            })
            searchBoxResponsive.classList.toggle('appear')
        })

        mainNavSearch.addEventListener('click', _ => {
            mainNavItems.forEach(item => {
                item.classList.toggle('disappear')
            })
            searchBoxMain.classList.toggle('appear')
        })

    }
}
</script>