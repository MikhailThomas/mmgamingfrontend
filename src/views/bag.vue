<template>
  <div id="page" class="container">
    <div id="heading" class="py-1 my-3">
      <h1><span class="glyphicon glyphicon-shopping-cart"></span> Shopping Cart</h1>
							</div>
					<div id="table" class="row mt-2">
						<div class="col-3 my-auto"><img id="product" class="img-responsive" src="https://i.postimg.cc/Y97TSQsG/card.png">
						</div>
						<div class="col-4 my-auto">
							<h4 class="product-name"><strong>Product name</strong></h4>
						</div>
                <div class="col-2 my-auto">
                  <h5>Quantity</h5>
                  <span class="my-auto"><h6>1</h6></span>
                </div>
              <div class="col-1 my-auto">
                <h5>Price</h5>
                <span class="my-auto"><h6><strong>R25.00<span class="text-muted">x</span></strong></h6></span>
              </div>
              <div class="col-lg-2 my-auto">
                <button type="button" class="btn btn-link">
                  <i class="bi bi-trash text-danger"></i>
								</button>
              </div>
          </div>
          <!-- end -->
          <div id="table2" class="row">
						<div class="col-1 my-auto"><img id="image" class="img-responsive" src="https://i.postimg.cc/SxXw9JKd/heavy.gif">
						</div>
            <div class="col-2 my-auto"><img id="image2" class="img-responsive" src="https://i.postimg.cc/sfk2G17J/metal-slug.gif">
						</div>
						<div class="col-4 my-auto">
							<h3 class="product-name mx-auto"><strong>TOTAL</strong></h3>
						</div>
                <div class="col-2 my-auto">
                  <h5>Quantity</h5>
                  <span class="my-auto"><h6>1</h6></span>
                </div>
              <div class="col-1 my-auto">
                <h5>Price</h5>
                <span class="my-auto"><h6><strong>R25.00<span class="text-muted">x</span></strong></h6></span>
              </div>
              <div class="col-lg-2 my-auto">
                <div class="user-box">
        <div class="login-box"> <a href="/card" >
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        Checkout
      </a>
        </div>
        </div>
              </div>
          </div>
				</div>
</template>

<script>
export default {

}
</script>

<style scoped>
#page{
  height: 100vh;
}
.container{
  padding-left: 0px;
  padding-right: 0px;
}

#heading{
  color: #03e9f4;
  background: rgba(255, 255, 255, 0.411);
}

#table{
  background: rgba(0, 0, 0, 0.914);
  color: rgb(255, 255, 255);
  justify-content: center;
  margin: auto;
  min-height: 100px;
}

#table2{
  color: rgba(0, 0, 0, 0.914);
  background: rgb(255, 255, 255);
  justify-content: center;
  margin: auto;
  min-height: 100px;
  border-bottom-right-radius: 20px;
  border-bottom-left-radius: 20px;
}
#product{
  max-width: 100px;
}

#image{
  max-width: 100px;
}

#image2{
  max-width: 100px;
  animation: run 7s linear infinite ;
}
@keyframes run {
  0% {
    transform:translateX(0px);
  }
  25% {
    transform:translateX(-70px);
  }
  50% {
    transform:translateX(0px);
  }
  75% {
    transform:translateX(180px);
  }
  85%{
    transform: translateX(90px);
  }
  100%{
    transform: translateX(0px);
  }
}


@media screen and (max-width: 400px) {
  #image{
  max-width: 50px;
}
  #image2{
  max-width: 50px;
  animation: smallrun 5s linear infinite ;
}
}
@keyframes smallrun {
  0% {
    transform:translateX(0px);
  }
  25% {
    transform:translateX(-30px);
  }
  50% {
    transform:translateX(0px);
  }
  75% {
    transform:translateX(30px);
  }
  100%{
    transform: translateX(0px);
  }
}

@media screen and (max-width: 800px) {
  #image{
  max-width: 70px;
}
  #image2{
  max-width: 70px;
  animation: mediumrun 5s linear infinite ;
}
}
@keyframes mediumrun {
  0% {
    transform:translateX(0px);
  }
  25% {
    transform:translateX(-30px);
  }
  50% {
    transform:translateX(0px);
  }
  75% {
    transform:translateX(40px);
  }
  100%{
    transform: translateX(0px);
  }
}

@media screen and (max-width: 950px) {
}
@keyframes mediumrun {
  0% {
    transform:translateX(0px);
  }
  25% {
    transform:translateX(-100px);
  }
  50% {
    transform:translateX(0px);
  }
  75% {
    transform:translateX(40px);
  }
  100%{
    transform: translateX(0px);
  }
}

@media screen and (max-width: 1200px) {
  #image{
  max-width: 70px;
}
  #image2{
  max-width: 70px;
  animation: largerun 5s linear infinite ;
}
}
@keyframes largerun {
  0% {
    transform:translateX(0px);
  }
  25% {
    transform:translateX(-35px);
  }
  50% {
    transform:translateX(0px);
  }
  75% {
    transform:translateX(45px);
  }
  100%{
    transform: translateX(0px);
  }
}

input{
  border: hidden;
}

/* checkout */
.login-box a {
  position: relative;
  display: inline-block;
  padding: 10px 5px;
  color: #03e9f4;
  text-decoration: none;
  text-transform: uppercase;
  overflow: hidden;
  transition: 0.5s;
}

.login-box a:hover {
  background: #03e9f4;
  color: #fff;
  border-radius: 5px;
  box-shadow: 0 0 5px #03e9f4, 0 0 25px #03e9f4, 0 0 50px #03e9f4,
    0 0 100px #03e9f4;
}

.login-box a span:nth-child(1) {
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

.login-box a span:nth-child(2) {
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

.login-box a span:nth-child(3) {
  width: 100%;
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

.login-box a span:nth-child(4) {
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

