<template>
    <div id="bookshelf-div">
            <p class="bookshelf-book-racks">
                Bookshelf & 
            </p>
            <p class="bookshelf-book-racks">
                Book Racks
            </p>
            <div id="lorem-ipsum-para">
            <p class="lorem-ipsum">
                Lorem Ipsum is simply dummy text of the printing and
            </p>
            <p class="lorem-ipsum">
                typesetting industry. Lorem Ipsum is simply dummy text
            </p>
            <p class="lorem-ipsum">
                of the printing and typesetting industry. Lorem Ipsum is
            </p>
            <p class="lorem-ipsum">
                simply dummy text of the printing and typesetting
            </p>
            <p class="lorem-ipsum">
                industry.
            </p>
            </div>
            <div id="book-category-title">
                <p class="book-category-title-para">
                    Hardcover Fiction
                </p>
            </div>
            
            <div id="carousel" ref="inputName">
            <button @click="scroll_left" style="background:inherit; position:unset; top: 50%; cursor: pointer; border: none; margin-left: -4%;"><img style="transform: scaleX(-1);" src="../assets/slider_arrow.png" alt=""></button>
            <div class="card-parent" @click="selectBook(book)" style="position:relative" v-for="book in books" :key="book.title">
                <div class="card">
                <img class="book-image" :src="'src/' + book.book_image" />
                <p class="rating-para">{{book.rating}} out of 5</p>
                <p class="title-para">{{book.title}}</p>
                <p class="author-para">{{book.author}}</p>
                </div>
            </div>
            
            <button @click="scroll_right" style="background:inherit; position: sticky; right: 0; top: 50%; cursor: pointer; border: none"><img src="../assets/slider_arrow.png" alt=""></button>
            
            </div>
            
            <div class="selected-div" v-if="bookSelected">
                <div style="display: flex; flex-direction: row; align-items: center; justify-content: space-between;">
                <p style="color:white; font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; opacity: .8;">{{selectedBook.title}}</p>
                <p style="margin-left: -25%;color:white; font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">{{selectedBook.title}}</p>
                <img style="cursor:pointer; padding-right: 2%;" @click="bookSelected = false" src="src/assets/close.png" alt="">
                </div>
                <div style="padding-top: 2.5%; display: flex;">
                <div style="display: flex;
    flex-direction: column;
    align-items: flex-start;">
                <img style="width: 80px; padding-bottom: 25%;" :src="'src/' + selectedBook.book_image" />
                <button style="cursor: pointer;font-size: 15px; font-weight: 500;background-color:#42454b; color: white; width: 180%; height: 20%; font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; border-radius: 4px; opacity: .8; border: none;">Add to Favorites +</button>
                </div>
                <div class="lorem-ipsum-dummy-text">
                    <p style="color:white; font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">Lorem Ipsum is simply dummy text of the printing and typesetting</p>
                    <p style="color:white; font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">industry. Lorem Ipsum has been the industry's standard dummy</p>
                    <p style="color:white; font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">text ever since the 1500sLorem Ipsum is simply dummy text of</p>
                    <p style="color:white; font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">the printing and typesetting industry. Lorem Ipsum has been the</p>
                    <p style="color:white; font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">industry's standard dummy text ever since the 1500sLorem</p>
                    <p style="color:white; font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">Ipsum is simply dummy text of the printing and typesetting</p>
                    <p style="color:white; font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">industry. Lorem Ipsum has been the industry's standard dummy</p>
                    <p style="color:white; font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">text ever since the 1500sLorem Ipsum is simply dummy text of</p>
                    <p style="color:white; font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">the printing and typesetting industry. Lorem Ipsum has been the</p>
                    <P style="color:white; font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">industry's standard dummy text ever since the 1500s</P>
                </div>
                </div>
            </div>

    </div>
</template>

<script>

import json from '../../seed/books.json'

export default {

data() {
  return {

    books: json.results.books,
    selectedBook: {},
    bookSelected: false


  }
},

methods: {
    selectBook(arg){
        this.selectedBook = arg;
        this.bookSelected = true;
        console.log(this.selectedBook);
    },
    scroll_right() {
//   let content = document.querySelector(".wrapper-box");
  this.$refs.inputName.scrollLeft += 210;
},
scroll_left(){
    this.$refs.inputName.scrollLeft -= 210;
}
    

},

created() {
    console.log(this.books)
}

}

</script>

<style>

    #bookshelf-div{
        padding-top:4%;
        padding-bottom:4%;
    }
    
    .bookshelf-book-racks{
        font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        font-size: 66px;
        font-weight: 100;
        font-stretch: normal;
        font-style: normal;
        line-height: 1.125;
        letter-spacing: normal;
        color: #fff;
        padding-left: 64px;
        margin: 0 0 0;
        max-width: 460px;
    }

    #lorem-ipsum-para{
        padding-top:2%;
    }

    .lorem-ipsum{
        font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        color: #fff;
        padding-left: 65px;
        margin: 0 0 0;
        max-width: 460px;
        font-size: 16px;
        font-weight: 300;
        font-stretch: normal;
        font-style: normal;
        line-height: 1.38;
        letter-spacing: .4px;
        opacity: 0.8;
    }

    #book-category-title{
        padding-top:6%;
    }

    .book-category-title-para{
        font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        font-size: 22px;
        padding-left: 65px;
        font-weight: 500;
        font-stretch: normal;
        font-style: normal;
        line-height: 1.27;
        letter-spacing: normal;
        color: #ffffff;
    }


    .book-image{
        width: 230px;
    }


    #carousel{ 
        padding-left: 65px;
        padding-top: 18px;
        height: fit-content;
        display: flex;
        position: relative;
        gap: 1rem;
        overflow-x: scroll;
    }
    #carousel::-webkit-scrollbar{
        /* background: transparent; */
        /* height: 0.5rem; */
        display: none;
    }

    #carousel::-webkit-scrollbar-thumb{
        background: #fff;
        border-radius: 1rem;
    }

    .card img{
        border-radius: 10px;
    }

    .card{
        width: 16%;
        box-shadow:  -160px 260px 160px 48px black;
    }

    .card-parent{
        cursor: pointer;
    }

    .card-parent:hover{
        transform: scale(1.1);
        padding-left: 2%;
        padding-right: 2%;
    }

    .rating-para{
        background-color: #003366;color: white; position: absolute; top: -16px; right: 0px; opacity: 0.90;
        font-size: 16px;
        font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        font-weight: 400;
        font-stretch: normal;
        font-style: normal;
        line-height: normal;
        letter-spacing: .2px;
        padding-left: 4px;
        padding-right: 4px;
        border-bottom-left-radius: 10px;
        border-top-right-radius: 10px;
    }

    .title-para{
        color: white; position: absolute; bottom: 50px; font-size: 18px;
        font-weight: 500;
        font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        font-stretch: normal;
        font-style: normal;
        line-height: 1.2;
        letter-spacing: -.2px;
        padding-left: 8px;
        padding-right: 4px;
        color: #fff;
        max-width: 100%;
        margin: 0 0 7px;
        z-index: 1;
    }

    .author-para{
        color: white;
        position: absolute; bottom: 20px; font-size: 18px;
        font-weight: 500;
        font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        font-stretch: normal;
        font-style: normal;
        line-height: 1.2;
        letter-spacing: -.2px;
        padding-left: 8px;
        padding-right: 4px;
        color: hsla(0,0%,100%,.8);
        max-width: 100%;
        margin: 0 0 7px;
        z-index: 1;
    }

    .selected-div{
        padding-top: 5%;
        padding-left: 5%;
    }

    .lorem-ipsum-dummy-text{
        line-height: 0.4;
        opacity: 0.4;
        margin-left: 25%;
}
    

</style>