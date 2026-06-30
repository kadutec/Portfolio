<template>
  <header class="header">
    <div class="container">

      <div class="logo">
        Carlos.
      </div>

      <nav>

        <ul>

          <li>
            <a href="#about">about</a>
          </li>

          <li>
            <a href="#skills">skills</a>
          </li>

          <li>
            <a href="#projects">projects</a>
          </li>

          <li>
            <a href="#contact">contact</a>
          </li>

        </ul>

      </nav>

    </div>
  </header>
</template>

<script setup>

</script>

<style scoped>

.header{

    position:absolute;

    width:100%;

    top:0;

    left:0;

    z-index:100;

    padding:35px 0;

}

.container{

    max-width:1400px;

    margin:auto;

    display:flex;

    justify-content:space-between;

    align-items:center;

}

.logo{

    color:white;

    font-size:32px;

    font-weight:800;

    letter-spacing:1px;

}

ul{

    display:flex;

    list-style:none;

    gap:45px;

}

a{

    color:white;

    text-decoration:none;

    font-size:17px;

    font-weight:600;

    transition:.3s;

}

a:hover{

    color:#d7b6ff;

}

@media(max-width:991px){

    .container{

        padding:0 25px;

    }

    ul{

        gap:25px;

    }

}

@media(max-width:768px){

    nav{

        display:none;

    }

}

</style>