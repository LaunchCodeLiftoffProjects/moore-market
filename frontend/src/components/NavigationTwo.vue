<template>
    <div>
        <div class="jumbotron jumbotron-fluid mb-0">
            <div class="container">
                <h1 class="display-3 text-left">Moore Market</h1>
            </div>
        </div>
        <nav class="navbar  navbar-expand-lg navbar-light bg-light" style="background: linear-gradient(-90deg, #84CF6A, #16C080);">
            <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>

            <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <ul class="navbar-nav mr-auto">
                <li class="nav-item">
                    <router-link to="/" class="nav-link" exact >Home</router-link>
                </li>
                <li class="nav-item">
                    <router-link to="/dashboard" class="nav-link" >Dashboard</router-link>
                </li>
                <li class="nav-item">
                    <router-link to="/product/add" class="nav-link" >Add Product</router-link>
                </li>
                <li class="nav-item dropdown">
                    <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                    Vendors
                    </a>
                    <div class="dropdown-menu" aria-labelledby="navbarDropdown">
                    <a class="dropdown-item" href="#">Action</a>
                    <a class="dropdown-item" href="#">Another action</a>
                    <div class="dropdown-divider"></div>
                        <a class="dropdown-item" href="#">Something else here</a>
                    </div>
                </li>
                <li class="nav-item">
                    <a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Register</a>
                </li>
                <li class="nav-item">
                </li>    
            </ul>

            <form action="/products/search" class="form-inline my-2 my-lg-0">
            <input class="form-control mr-sm-2" type="search" name="searchTerm" placeholder="Search" aria-label="Search">
            <button class="btn btn-dark my-2 my-sm-0" type="submit">Search</button>
            </form>
            <router-link :to="{name: 'ShoppingCart'}" class="btn btn-dark my-2 mx-1 my-sm-0"><img src="../assets/cart.png" width="24" height="24" class="d-inline-block align-top img thumbnail" alt="">Shopping Cart</router-link>

            </div>    
        </nav>
    </div>

</template>

<script>
export default {
  name: 'NavigationTwo',
  computed: {
    cart() {
      return this.$store.state.product.cart
    }
  }
}
</script>

<style>

.jumbotron {
    opacity: 0.7;
    background-image: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0,0,0,0.7)), url("../assets/fruits and vegetables carts.svg");
    background-attachment: fixed;
    background-size: cover;
}

.jumbotron h1{
    color: white;
}

</style>
