<template>
  <div class="home">
        <div class="container p-0">
      <!-- header -->
          <header class="header">
            <div id="carouselExampleSlidesOnly" class="carousel slide" data-ride="carousel">
              <div class="carousel-inner">
                <div class="carousel-item active">
                  <img class="d-block w-100" src="../assets/avatar-1.jpg" alt="First slide">
                </div>
                <div class="carousel-item">
                  <img class="d-block w-100" src="../assets/avatar-2.jpg" alt="Second slide">
                </div>
                <div class="carousel-item">
                  <img class="d-block w-100" src="../assets/avatar-3.jpg" alt="Third slide">
                </div>
                <div class="carousel-item">
                  <img class="d-block w-100" src="../assets/avatar-4.jpg" alt="Fourth slide">
                </div>
                <div class="carousel-item">
                  <img class="d-block w-100" src="../assets/avatar-5.jpg" alt="Fifth slide">
                </div>
                <div class="carousel-item">
                  <img class="d-block w-100" src="../assets/avatar-6.jpg" alt="Sixth slide">
                </div>
              </div>
            </div>
          </header>
          <!-- header ends here -->

          <main class="main">

            <section class="section-comment">
              <div class="heading">
                <h2 class="heading__secondary">
                  Add your own comment here...
                </h2>
              </div>

              <form action="#" class="form" >
                <div class="form__container">
                  <div class="form__group">
                    <label for="name">Your name: </label>
                    <input type="text" name="name" id="name" class="form__input" placeholder="Your name...">
                  </div>
                  <div class="form__group">
                    <label for="message">Your comment:</label>
                    <textarea name="comment" id="message" rows="5" cols="30" class= "form__area" placeholder="message here..."></textarea>
                  </div>
                </div>

                <div class="button-box">
                  <button type="submit" class="col-12 button">Post</button>
                </div>

              </form>
            </section>
            <section class="section-gallery">

              <div class="comment">
                <div class="comment__heading">
                  <h2 class="heading-secondary">
                    Comments
                  </h2>
                </div>

                <div class="comment__container">
                  <div class="comment__box">
                    <div class="comment__avatar">
                      <img src="images/avatar-anisha.png" alt="avatar image" class="comment__image">
                    </div>
                    <div class="comment__title">
                      <h3 class="heading__tertiary">name</h3>
                    </div>

                    <p class="comment__text">
                      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Libero, deleniti!
                      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Libero, deleniti!
                      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Libero, deleniti!
                      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Libero, deleniti!
                      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Libero, deleniti!
                    </p>
                  </div>

                  <div class="comment__box">
                    <div class="comment__avatar">
                      <img src="images/avatar-anisha.png" alt="avatar image" class="comment__image">
                    </div>
                    <div class="comment__title">
                      <h3 class="heading__tertiary">name</h3>
                    </div>
                    <p class="comment__text">
                      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Libero, deleniti!
                      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Libero, deleniti!
                      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Libero, deleniti!
                      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Libero, deleniti!
                      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Libero, deleniti!
                    </p>
                  </div>
                  <div class="comment__box">
                    <div class="comment__avatar">
                      <img src="images/avatar-anisha.png" alt="avatar image" class="comment__image">
                    </div>
                    <div class="comment__title">
                      <h3 class="heading__tertiary">name</h3>
                    </div>
                    <p class="comment__text">
                      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Libero, deleniti!
                      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Libero, deleniti!
                      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Libero, deleniti!
                      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Libero, deleniti!
                      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Libero, deleniti!
                    </p>
                  </div>
                  <div class="comment__box">
                    <div class="comment__avatar">
                      <img src="images/avatar-anisha.png" alt="avatar image" class="comment__image">
                    </div>
                    <div class="comment__title">
                      <h3 class="heading__tertiary">name</h3>
                    </div>
                    <p class="comment__text">
                      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Libero, deleniti!
                      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Libero, deleniti!
                      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Libero, deleniti!
                      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Libero, deleniti!
                      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Libero, deleniti!
                    </p>
                  </div>
                </div>
              </div>
              <button class="btn btn--more">
                See more! <span>&rarr;</span>
              </button>
            </section>
          </main>
          <footer class="footer">
            <div class="footer__text">
              Built by <span class="highlight">Tolulope Adebesin</span>; 
             <p class="footer__paragraph">Copyright&copy; 2020 by Tolulope Adebesin (His first Son) </p>
            </div>
          </footer>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import $ from 'jquery/dist/jquery.js'
export default {
  name: 'Home',
  components: {
    // HelloWorld
  },
  data(){
    return{

    }
  },
  mounted(){
    $('.carousel').carousel({
    interval: 1000
  },
  "cycle"
  )
  }
}
</script>
