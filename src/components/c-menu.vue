<template>
    <div class="row menu">
        <div class="menu_item"><router-link to="/home">Home</router-link></div>
        <div class="menu_item">Cart</div>
        <div class="menu_item">Account</div>
    </div>
</template>

<style>
.row {
    display: flex;
    flex-wrap: inherit;
    justify-content: space-around;
    position: relative;
}

.menu {
    height: 50px; 
    position: fixed; 
    bottom:0%;
    width:100%;  
    opacity: 1;
    border-top: 0.5px solid black;
    background-color: white;
}
.menu_item {
    position: relative;
    margin: 0;
    top: 25%;
}
</style>