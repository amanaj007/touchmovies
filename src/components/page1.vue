<template>
    <div>
        <div id="nav-div">
            <nav>

        
                <ul>
                    <li id="logo-img">
                        <a href="">
                            <img src="../assets/bmuse_logo.png" id="bmuse-img" alt="">
                        </a>
                    </li>
                    <li id="search-img">
                        <div id="search-img-div">
                            <img src="../assets/search.png" alt="">
                        </div>
                    </li>
                </ul>
            </nav>
        </div>
        
    </div>

</template>

<script>

</script>

<style scoped>

    ul{
        display: flex;
        justify-content: space-between;
    }

    li{ list-style: none;}


    #logo-img{
        float: left;
    }

    #bmuse-img{
        width: 70%;
    }

    #search-img{
        place-self: center;
        padding-right: 1%;
    }

    #search-img-div{
        height: 35px;
        width: 35px;
        background-color: black;
        border-radius: 50%;
        display: inline-block;
        display: flex;
        justify-content: center;
        align-items: center;
        margin-top: -20%;
    }

</style>