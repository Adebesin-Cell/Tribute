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
              <form action="#" class="form" @submit.prevent="postMessage">
                <div class="alert alert-success" role="alert" v-if="feedback">
                  Messsage Posted Successfully !
                </div>
                <div class="form__container">
                  <div class="form__group">
                    <label for="name">Your name: </label>
                    <input type="text" name="name" id="name" v-model="name" class="form__input" placeholder="Your name...">
                  </div>
                  <div class="form__group">
                    <label for="message">Your comment:</label>
                    <textarea name="comment" id="message" v-model="message" rows="5" cols="30" class= "form__area" placeholder="message here..."></textarea>
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

                <paginate name="messages" :list="messages" :per="5" v-if="shown">
             <!-- <div class="col-md-12 mb-4" v-for="(blog, index) in paginated('blogs')" :key="index"> -->
                 <!-- <div class="card">
                     <div class="card-body">
                         <div class="row">
                             <div class="col-md-2">
                                 <img src="@/assets/blog.jpg" alt="" class="img-fluid">
                             </div>
                             <div class="col-md-10 text-left">
                                 <router-link :to="'viewBlogs/' + blog.id" class="h5 font-weight-bold text-dark">{{blog.title}}</router-link>
                                 <p>{{blog.body}}</p>
                             </div>
                         </div>
                     </div>
                 </div> -->
             <!-- </div> -->
                <!-- <div class="comment__container"> -->
                  <div class="comment__box" v-for="(message, index) in paginated('messages')" :key="index">
                    <div class="comment__avatar">
                      <img src="../assets/avatar-anisha.png" alt="avatar image" class="comment__image">
                    </div>
                    <div class="comment__title">
                      <h3 class="heading__tertiary">{{message.name}}</h3>
                    </div>

                    <p class="comment__text">
                     {{message.message}}
                    </p>
                  </div>
                <!-- </div> -->
             </paginate>

              </div>
              <!-- <button class="btn btn--more">
                See more! <span>&rarr;</span>
              </button> -->
              <div class="pagination text-center">
                    <paginate-links for="messages" :async="true" :show-step-links="true" :step-links="{
                        next: 'Next',
                        prev: 'Prev' }" class="page-links pagination text-center">
                    </paginate-links>
                </div>
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
import $ from 'jquery/dist/jquery.js'
export default {
  name: 'Home',
  data(){
    return{
      messages: [],
      name: '',
      message: '',
      feedback: false,
      paginate: ['messages'],
      shown: false
    }
  },
  methods:{
    postMessage(){
      this.axios.post('https://tribute-27bf0-default-rtdb.firebaseio.com/message.json',{
        name: this.name,
        message: this.message
      }).then(response =>{
        console.log(response)
        this.feedback = true
        location.reload()
        this.shown = true

      })
    },
    showMessage(){
      this.axios.get('https://tribute-27bf0-default-rtdb.firebaseio.com/message.json').then(response =>{
      console.log(response.data)
      for(let key in response.data){
        response.data[key].id = key
        this.messages.unshift(response.data[key])
        console.log(this.messages)
        this.shown = true
      }
    })
    }
  },
  mounted(){
    $('.carousel').carousel({
    interval: 1000
  },"cycle");

  },
  created(){
    this.showMessage()
  }
}
</script>
<style>
.pagination{
    margin: 0 auto !important;
}
.page-links{
    text-align: center !important;
}
.pagination .left-arrow a, .pagination .right-arrow a{
    background: #041705 !important;
    color: #fff !important;
    padding: 8px 10px !important;
    cursor: pointer !important;
}
.pagination .right-arrow a{
    margin-left: 8px;
}
.number a{
    color: #041705 !important;
    margin-left: 10px;
    cursor: pointer !important;
}
.number.active a{
        background: #041705 !important;
    color: #fff !important;
    padding: 4px;
}
</style>
