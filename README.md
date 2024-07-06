npm i razorpay
var instance = new Razorpay({
    key_id: 'rzp_live_icFIWGzQ1ImgRg
',
    key_secret: '8PFW4UpyB9IjwCpdF7Ddl4jU
',
  });// API signature
  // {razorpayInstance}.{resourceName}.{methodName}(resourceId [, params])
  
  // example
  
  instance.payments.fetch(paymentId)instance.payments.all({
    from: '2016-08-01',
    to: '2016-08-20'
  }).then((response) => {
    // handle success
  }).catch((error) => {
    // handle error
  })instance.payments.all({
    from: '2016-08-01',
    to: '2016-08-20'
  }, (error, response) => {
    if (error) {
      // handle error
    } else {
      // handle success
    }
  })const Razorpay = require('razorpay');
  var instance = new Razorpay({ key_id: 'rzp_live_icFIWGzQ1ImgRg
', key_secret: '8PFW4UpyB9IjwCpdF7Ddl4jU
T' })
  
  var options = {
    amount: 50000,  // amount in the smallest currency unit
    currency: "INR",
    receipt: "order_rcptid_11"
  };
  instance.orders.create(options, function(err, order) {
    console.log(order);
  });var orderId ;
  $(document).ready(function(){
      var settings = {
    "url": "/create/orderId",
    "method": "POST",
    "timeout": 0,
    "headers": {
      "Content-Type": "application/json"
    },
    "data": JSON.stringify({
      "amount": "50000"
    }),
  };
  
  //creates new orderId everytime
  $.ajax(settings).done(function (response) {
  
    orderId=response.orderId;
    console.log(orderId);
    $("button").show();
  });
  });<button id="rzp-button1">Pay with Razorpay</button>
  <script src="https://checkout.razorpay.com/v1/checkout.js"></script>
  <script>
  var options = {
      "key": "YOUR_KEY_ID", // Enter the Key ID generated from the Dashboard
      "amount": "50000", // Amount is in currency subunits. Default currency is INR. Hence, 50000 refers to 50000 paise
      "currency": "INR",
      "name": "Acme Corp",
      "description": "Test Transaction",
      "image": "https://example.com/your_logo",
      "order_id": "order_IluGWxBm9U8zJ8", //This is a sample Order ID. Pass the `id` obtained in the response of Step 1
      "handler": function (response){
          alert(response.razorpay_payment_id);
          alert(response.razorpay_order_id);
          alert(response.razorpay_signature)
      },
      "prefill": {
          "name": "Gaurav Kumar",
          "email": "gaurav.kumar@example.com",
          "contact": "9000090000"
      },
      "notes": {
          "address": "Razorpay Corporate Office"
      },
      "theme": {
          "color": "#3399cc"
      }
  };
  var rzp1 = new Razorpay(options);
  rzp1.on('payment.failed', function (response){
          alert(response.error.code);
          alert(response.error.description);
          alert(response.error.source);
          alert(response.error.step);
          alert(response.error.reason);
          alert(response.error.metadata.order_id);
          alert(response.error.metadata.payment_id);
  });
  document.getElementById('rzp-button1').onclick = function(e){
      rzp1.open();
      e.preventDefault();
  }
  </script>"handler": function (response){
    alert(response.razorpay_payment_id);
    alert(response.razorpay_order_id);
    alert(response.razorpay_signature)}{
        "razorpay_payment_id": "pay_29QQoUBi66xm2f",
        "razorpay_order_id": "order_9A33XWu170gUtm",
        "razorpay_signature": "9ef4dffbfd84f1318f6739a3ce19f9d85851857ae648f114332d8401e0949a3d"
      }generated_signature = hmac_sha256(order_id + "|" + razorpay_payment_id, secret);

      if (generated_signature == razorpay_signature) {
        payment is successful
      }var instance = new Razorpay({ key_id: 'rzp_live_icFIWGzQ1ImgRg
', key_secret: '8PFW4UpyB9IjwCpdF7Ddl4jU
' })

      var { validatePaymentVerification, validateWebhookSignature } = require('./dist/utils/razorpay-utils');
      validatePaymentVerification({"order_id": razorpayOrderId, "payment_id": razorpayPaymentId }, signature, secret);var settings = {
        "url": "/api/payment/verify",
        "method": "POST",
        "timeout": 0,
        "headers": {
          "Content-Type": "application/json"
        },
        "data": JSON.stringify({response}),
      }
