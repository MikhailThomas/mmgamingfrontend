<template>
  <div class="content-profile-page">
    <div class="profile-user-page card">
      <div class="img-user-profile">
        <img
          class="profile-bgHome"
          src="https://i.postimg.cc/Vv4GDSyb/card.png"
        />
      </div>
      <div class="user-profile-data">
        <h1>mikhail{{ name / surname }}</h1>
        <button>change image</button>
        <p>email{{ email }}</p>
      </div>
      <div class="description-profile">
        <strong> date created </strong>
      </div>
      <ul class="data-user">
        <li>
          <a
            ><strong>logout{{ logout }}</strong></a
          >
        </li>
        <li>
          <a
            ><strong><bag /></strong
          ></a>
        </li>
        <li>
          <a><strong>Delete acc</strong></a>
        </li>
      </ul>
    </div>
  </div>
  <!-- table -->
  <section id="admin">
    <div id="con" class="container" v-if="products">
      <!-- nav -->
      <div class="row justify-content-center">
        <!-- ___________ -->
        <div id="table" class="col-sm-1 mb-1"></div>
        <!--  -->
        <div id="table" class="d-flex justify-content-between px-5">
          <h1 class="text-start">ADMIN</h1>
          <div class="side back-card">
            <div class="login-box">
              <form>
                <button
                  type="button"
                  class="btn"
                  data-bs-toggle="modal"
                  data-bs-target="#exampleModal"
                >
                  <b>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    ADD PRODUCTS
                  </b>
                </button>
              </form>
            </div>
          </div>
        </div>
      </div>
      <!-- --------- -->
      <div
        class="modal fade"
        id="exampleModal"
        tabindex="-1"
        aria-labelledby="exampleModalLabe2"
        aria-hidden="true"
      >
        <div class="modal-dialog">
          <div class="modal-content">
            <div class="modal-header">
              <h5 class="modal-title" id="exampleModalLabel">Add Products</h5>
              <button
                type="button"
                class="btn-close"
                data-bs-dismiss="modal"
                aria-label="Close"
              ></button>
            </div>
            <div class="modal-body">
              <div>
                <label for="name">Title: </label>
                <input
                  type="name"
                  maxlength="20"
                  required
                  id="add-title"
                  v-model="title"
                />
              </div>
              <div>
                <label for="price">Genre: </label>
                <input type="name" required id="add-Genre" v-model="genre" />
              </div>
              <div>
                <label for="img">url: </label>
                <input type="name" required id="add-Price" v-model="img" />
              </div>
              <div>
                <div>
                  <label for="name">Description: </label>
                  <input
                    type="text"
                    required
                    id="add-Description"
                    v-model="description"
                  />
                </div>
                <div>
                  <label for="name">Price: </label>
                  <input
                    type="number"
                    required
                    id="add-Price"
                    v-model="price"
                  />
                </div>
                <div>
                  <label for="name">Quantity: </label>
                  <input
                    type="number"
                    required
                    id="add-Quantity"
                    v-model="quantity"
                  />
                </div>
              </div>
            </div>
            <div class="modal-footer">
              <button type="button" id="closeBtn" data-bs-dismiss="modal">
                Close
              </button>
              <button
                type="button"
                id="addWig-Btn"
                data-bs-dismiss="modal"
                @click="Add"
              >
                <i class="bi bi-plus-circle"></i>
                Add Product
              </button>
            </div>
          </div>
        </div>
      </div>
      <!-- ____________________ -->
      <div class="row justify-content-center">
        <!-- table -->
        <div id="table1" class="col-sm-11">
          <table class="table table-bordered">
            <thead>
              <th>ID</th>
              <th>Title</th>
              <th>img</th>
              <th>genre</th>
              <th>description</th>
              <th>price</th>
              <th>Quantity</th>
              <th>createdby</th>
              <th>Actions</th>
            </thead>
            <tbody>
              <tr v-for="(product, index) in products" :key="index">
                <td class="px-3">{{ product.productid }}</td>
                <td>{{ product.title }}</td>
                <td>
                  <img
                    class="rounded text-center justify-content-center mx-1"
                    :src="product.img"
                    alt=""
                  />
                </td>
                <td>{{ product.genre }}</td>
                <td id="description">"{{ product.description }}"</td>
                <td>R{{ product.price }}</td>
                <td>{{ product.quantity }}</td>
                <td>{{ product.createdby }}</td>
                <td>
                  <div class="row">
                    <div class="col-12">
                      <button
                        id="delete"
                        class="b btn-layout"
                        v-on:click="
                          $store.dispatch('deleteuser', product.Productid)
                        "
                      >
                        <i class="bi bi-trash text-danger"></i>
                      </button>
                    </div>
                    <div class="col-12">
                      <button
                        type="button"
                        class="btn"
                        data-bs-toggle="modal"
                        :data-bs-target="'#edit' + product.productid"
                      >
                        <i class="bi bi-brush"></i>
                      </button>
                      <!-- modal-edit -->
                      <div
                        class="modal fade"
                        :id="'edit' + product.productid"
                        tabindex="-1"
                        aria-labelledby="exampleModalLabe2"
                        aria-hidden="true"
                      >
                        <div class="modal-dialog">
                          <div class="modal-content">
                            <div class="modal-header">
                              <h5 class="modal-title">Edit Products</h5>
                              <button
                                type="button"
                                class="btn-close"
                                data-bs-dismiss="modal"
                                aria-label="Close"
                              ></button>
                            </div>
                            <div class="modal-body">
                              <div>
                                <label for="name">Title: </label>
                                <input
                                  type="name"
                                  maxlength="20"
                                  required
                                  id="add-title"
                                  v-model="product.title"
                                />
                              </div>
                              <div>
                                <label for="price">Genre: </label>
                                <input
                                  type="name"
                                  required
                                  id="add-Genre"
                                  v-model="product.genre"
                                />
                              </div>
                              <div>
                                <label for="img">url: </label>
                                <input
                                  type="name"
                                  required
                                  id="add-Price"
                                  v-model="product.img"
                                />
                              </div>
                              <div>
                                <div>
                                  <label for="name">Description: </label>
                                  <input
                                    type="text"
                                    required
                                    id="add-Description"
                                    v-model="product.description"
                                  />
                                </div>
                                <div>
                                  <label for="name">Price: </label>
                                  <input
                                    type="number"
                                    required
                                    id="add-Price"
                                    v-model="product.price"
                                  />
                                </div>
                                <div>
                                  <label for="name">Quantity: </label>
                                  <input
                                    type="number"
                                    required
                                    id="add-Quantity"
                                    v-model="product.quantity"
                                  />
                                </div>
                              </div>
                            </div>
                            <div class="modal-footer">
                              <button
                                type="button"
                                id="closeBtn"
                                data-bs-dismiss="modal"
                              >
                                Close
                              </button>
                              <button
                                type="button"
                                id="addWig-Btn"
                                data-bs-dismiss="modal"
                                @click="$store.dispatch('EditProduct')"
                              >
                                <i class="bi bi-plus-circle"></i>
                                Edit Product
                              </button>
                            </div>
                          </div>
                        </div>
                      </div>
                      <!-- ------ -->
                      <!-- modal delete -->

                      <!-- ----------- -->
                    </div>
                  </div>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>

    <div v-else>
      <div class="loader">
        <svg viewBox="0 0 80 80">
          <circle id="test" cx="40" cy="40" r="32"></circle>
        </svg>
      </div>

      <div class="loader triangle">
        <svg viewBox="0 0 86 80">
          <polygon points="43 8 79 72 7 72"></polygon>
        </svg>
      </div>

      <div class="loader">
        <svg viewBox="0 0 80 80">
          <rect x="8" y="8" width="64" height="64"></rect>
        </svg>
      </div>
    </div>
  </section>
</template>

<script>
import bag from '../components/bag.vue'
export default {
    components: {
        bag
    },
    data() {
    return {
      img: "https://i.postimg.cc/sx3W1SbS/logo2.png",
      quantity: 1,
      price: "",
      description: "",
      title: "",
      genre:"",
    }},
  mounted() {
    this.$store.dispatch("getProducts");
  },
 methods: {
    Add() {
      return this.$store.dispatch("addProduct", {
        title: this.title, // this returns as a empty string
        img: this.img,
        quantity: this.quantity,
        price: this.price, // this returns as a empty string
        genre: this.genre, // this returns as a empty string
        description:this.description // this returns as a empty string
      });
    },
  },

  computed: {
    products() {
      return this.$store.state.products;
    },
    user(){
      return this.$store.state.users;
    }
  },
};
</script>

<style scoped>
#userImage {
  max-width: 100%;
  max-height: 100%;
}
.content-profile-page {
  margin: auto;
  margin-top: 1rem;
  margin-bottom: 1rem;
  max-width: 50rem;
}

.card {
  background: rgb(0, 0, 0);
  border-radius: 0.3rem;
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.2);
  border: 0.1em solid rgba(0, 0, 0, 0.2);
}
.profile-user-page .img-user-profile .profile-bgHome {
  height: 16em;
}
.profile-user-page .img-user-profile .avatar {
  margin: auto;
  background: #fff;
  width: 7em;
  height: 7em;
  padding: 0.25em;
  border-radius: 0.4em;
  margin-top: -10em;
  box-shadow: 0 0 0.1em rgba(0, 0, 0, 0.35);
}
.profile-user-page button {
  cursor: pointer;
  background: #3498db;
  border: 1px solid #2487c9;
  color: #fff;
  border-radius: 0 0.6em 0 0.6em;
  padding: 0.8em;
}
.profile-user-page .user-profile-data,
.profile-user-page .description-profile {
  text-align: center;
}
.profile-user-page .user-profile-data h1 {
  margin-top: 5px;
  margin-bottom: 10px;
  color: #ffffff;
}
.profile-user-page .data-user {
  margin-bottom: 0;
  cursor: pointer;
  padding: 0;
  list-style: none;
  display: table;
  width: 100%;
}
.profile-user-page .data-user li {
  margin: 0;
  padding: 0;
  width: 33.33334%;
  display: table-cell;
  text-align: center;
  border-left: 0.1em solid transparent;
}
.profile-user-page .data-user li a,
.profile-user-page .data-user li strong {
  display: block;
}
.profile-user-page .data-user li a {
  background-color: #000000;
  color: white;
  border-bottom: 0.2em solid #f7f7f7;
  padding: 0.93em 0;
}
.profile-user-page .data-user li a strong,
.profile-user-page .data-user li a span {
  font-weight: 600;
  line-height: 1;
}
.profile-user-page .data-user li a strong {
  font-size: 2em;
}
.profile-user-page .data-user li a:hover {
  background: rgba(0, 0, 0, 0.05);
  border-bottom: 0.2em solid #3498db;
  color: #3498db;
}
/* table */
h1 {
  color: #03e9f4;
}
#con {
  background-color: rgb(0, 0, 0);
}

.table {
  color: white;
  overflow-x: scroll;
}
#table1 {
  border-top: 0.3px solid rgba(128, 128, 128, 0.282);
  border-left: 0.3px solid rgba(128, 128, 128, 0.282);
  border-right: 0.3px solid rgba(128, 128, 128, 0.282);
}

thead {
  font-size: 1.5rem;
}
th {
  font-size: 1rem;
  padding: 5px;
  border-top: none;
  border-left: 0.3px solid rgba(128, 128, 128, 0.282);
  border-right: 0.3px solid rgba(128, 128, 128, 0.282);
}

img {
  height: 10vh;
}

#description {
  font-size: 13px;
  font-weight: bold;
}

/* button */
.b:before {
  text-align: center;
  transition: all 0.3s ease-in-out;
  content: "";
  width: 0;
  height: 100%;
  background-color: rgb(0, 0, 0);
  color: rgb(255, 255, 255);
  transition: 0.3s;
}

.b:hover:before {
  color: rgb(255, 255, 255);
  box-shadow: 12px 31px 37px rgba(255, 255, 255, 0.5);
  width: 100%;
}

.btn-layout {
  display: inline-flex;
  opacity: 0.999;
  background-color: #00000000;
  text-align: center;
  color: rgb(0, 0, 0);
  border: none;
  -moz-transition: 0.3s;
  -ms-transition: 0.3s;
  -o-transition: 0.3s;
  -webkit-transition: 0.3s;
  transition: 0.3s;
}

.btn-layout:hover {
  background-color: rgba(0, 0, 0, 0.367);
}

.bi-brush {
  color: #03e9f4;
}

/* addproducts */

.login-box form b {
  position: relative;
  display: inline-block;
  padding: 10px 20px;
  color: #03e9f4;
  font-size: 16px;
  text-decoration: none;
  text-transform: uppercase;
  overflow: hidden;
  transition: 0.5s;
  /* margin-top: 40px; */
  letter-spacing: 4px;
}

.login-box b:hover {
  background: #03e9f4;
  color: #fff;
  border-radius: 5px;
  box-shadow: 0 0 5px #03e9f4, 0 0 25px #03e9f4, 0 0 50px #03e9f4,
    0 0 100px #03e9f4;
}

.login-box b span {
  position: absolute;
  display: block;
}

.login-box b span:nth-child(1) {
  top: 0;
  left: -100%;
  width: 100%;
  height: 2px;
  background: linear-gradient(90deg, transparent, #03e9f4);
  animation: btn-anim1 1s linear infinite;
}

@keyframes btn-anim1 {
  0% {
    left: -100%;
  }
  50%,
  100% {
    left: 100%;
  }
}

.login-box b span:nth-child(2) {
  top: -100%;
  right: 0;
  width: 2px;
  height: 100%;
  background: linear-gradient(180deg, transparent, #03e9f4);
  animation: btn-anim2 1s linear infinite;
  animation-delay: 0.25s;
}

@keyframes btn-anim2 {
  0% {
    top: -100%;
  }
  50%,
  100% {
    top: 100%;
  }
}

.login-box b span:nth-child(3) {
  bottom: 0;
  right: -100%;
  width: 100%;
  height: 2px;
  background: linear-gradient(270deg, transparent, #03e9f4);
  animation: btn-anim3 1s linear infinite;
  animation-delay: 0.5s;
}

@keyframes btn-anim3 {
  0% {
    right: -100%;
  }
  50%,
  100% {
    right: 100%;
  }
}

.login-box b span:nth-child(4) {
  bottom: -100%;
  left: 0;
  width: 2px;
  height: 100%;
  background: linear-gradient(360deg, transparent, #03e9f4);
  animation: btn-anim4 1s linear infinite;
  animation-delay: 0.75s;
}

@keyframes btn-anim4 {
  0% {
    bottom: -100%;
  }
  50%,
  100% {
    bottom: 100%;
  }
}
</style>