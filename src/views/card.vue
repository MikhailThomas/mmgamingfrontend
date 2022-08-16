<template>
  <div class="container">
    <bag />
    <!-- Button trigger modal -->
    <button
      type="button"
      class="btn btn-primary"
      data-bs-toggle="modal"
      data-bs-target="#exampleModal"
    >
      Pay over here
    </button>

    <!-- Modal -->
    <div
      class="modal fade"
      id="exampleModal"
      tabindex="-1"
      aria-labelledby="exampleModalLabel"
      aria-hidden="true"
    >
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title" id="exampleModalLabel">
              Fill in details please
            </h5>
            <button
              type="button"
              class="btn-close"
              data-bs-dismiss="modal"
              aria-label="Close"
            ></button>
          </div>
          <div class="modal-body">
            <div id="card" class="card-checkout">
              <div class="card-logo">
                <img
                  id="logo"
                  src="https://i.postimg.cc/Vv4GDSyb/card.png"
                  alt=""
                />
              </div>
              <div class="card-options">
                <form class="card-details">
                  <input class="cc-name" placeholder="Card Holder" required />
                  <input
                    class="cc-number"
                    placeholder="Card Number"
                    data-numeric
                    required
                  />
                  <input
                    class="cc-expiry inline col-6"
                    placeholder="Expiry Date"
                    required
                  /><input
                    class="cc-cvc col-6"
                    placeholder="CVC"
                    data-numeric
                    required
                  />
                  <button class="button button-scan">Scan Card</button>
                </form>
              </div>
              <div class="card-confirm">
                <button class="button button-confirm">Complete Order</button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- <div id="page" class="container">
    <div id="card" class="card-checkout">
        <div class="card-logo"><img id="logo" src="https://i.postimg.cc/Vv4GDSyb/card.png" alt=""></div>
        <div class="card-options">
            <form class="card-details">
                <input class="cc-name" placeholder="Card Holder" required>
                <input class="cc-number" placeholder="Card Number" data-numeric required>
                <input class="cc-expiry inline" placeholder="Expiry Date" required><input class="cc-cvc" placeholder="CVC" data-numeric required>
                <button class="button button-scan">Scan Card</button>
            </form>
        </div>
        <div class="card-confirm">
            <button class="button button-confirm">Complete Order</button>
        </div>
    </div> -->
</template>

<script>
import bag from "../components/bag.vue";
export default {
  components: { bag },
  data() {
    return {};
  },
  mounted() {},
};
//         (function() {
//     var ccName = $('input.cc-name'),
//         ccNumber = $('input.cc-number'),
//         ccExpiry = $('input.cc-expiry'),
//         ccCVC = $('input.cc-cvc');

//     $('[data-numeric]').payment('restrictNumeric');

//     ccNumber.payment('formatCardNumber');
//     ccExpiry.payment('formatCardExpiry');
//     ccCVC.payment('formatCardCVC');

//     ccName.on('focus', function() {
//         $(this).data('placeholder', $(this).attr('placeholder'))
//         $(this).attr('placeholder', 'Name Surname');
//     }).blur(function() {
//         $(this).attr('placeholder', $(this).data('placeholder'))
//     });

//     ccNumber.on('focus', function() {
//         $(this).data('placeholder', $(this).attr('placeholder'))
//         $(this).attr('placeholder', 'xxxx xxxx xxxx xxxx');
//     }).blur(function() {
//         $(this).attr('placeholder', $(this).data('placeholder'))
//     });

//     ccExpiry.on('focus', function() {
//         $(this).data('placeholder', $(this).attr('placeholder'))
//         $(this).attr('placeholder', 'MM/YYYY');
//     }).blur(function() {
//         $(this).attr('placeholder', $(this).data('placeholder'))
//     });

//     ccCVC.on('focus', function() {
//         $(this).data('placeholder', $(this).attr('placeholder'))
//         $(this).attr('placeholder', 'xxxx');
//     }).blur(function() {
//         $(this).attr('placeholder', $(this).data('placeholder'))
//     });
// })();
//     }
// }
</script>

<style scoped>
#logo{
    max-width: 100%;
    max-height: 100%;
}
.card-checkout {
    margin: auto;
    margin-top: 2rem;
    margin-bottom: 2rem;
    width: 30%;
    min-width: 300px;
    height: 70%;
    border-top-left-radius: 10%;
    border-top-right-radius: 10%;
    min-height: 400px;
    box-shadow: 0px 1px 10px rgba(0, 0, 0, 0.4);
}

.card-logo {
    width: 100%;
    height:35%;
    background: url('http://digest.dx3canada.com/wp-content/uploads/2013/01/Visa-Logo.jpg');
    background-size: 100px 45px;
    background-repeat: no-repeat;
    background-position: center;
    background-color: rgb(0, 0, 0);
    border-top-left-radius: 10%;
    border-top-right-radius: 10%;
}

.card-options {
    width: 100%;
    height: 55%;
    padding: 10px;
    background-color: rgba(0, 0, 0, 0.555);
}

.card-details {
    width: 100%;
    height: 100%;
}

.card-details input {
    width: 100%;
    padding: 10px 20px;
    color: rgb(0, 0, 0);
    background-color: #ffffff;
    border: 0;
    font-weight: 500;
    text-transform: uppercase;
}

.card-details input.inline {
    margin-right: 1px;
}

.card-details input::-webkit-input-placeholder {
    color: #000000;
}

.card-details input::-moz-placeholder {
    color: #000000;
}

.card-details input:-moz-placeholder {
    color: #000000;
}

.card-details input:-ms-input-placeholder {
    color: #000000;
}

.card-details input:placeholder-shown {
    color: #000000;
}

.card-confirm {
    position: relative;
    width: 100%;
    height: 50px;
}

.button {
    width: 100%;
    color: #fff;
    font-family: Roboto;
    font-weight: 500;
    text-transform: uppercase;
    border: 0;
}

.button-confirm {
    height: 100%;
    background-color: #03e9f4;
    border-bottom-left-radius: 5px;
    border-bottom-right-radius: 5px;
    cursor: pointer;
}

.button-confirm:focus {
    outline: 0;
}

.button-scan {
    height: 15%;
    background-color: #62AEFA;
    cursor: pointer;
}
</style>
