<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Payment via Easypaisa</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      margin: 0; padding: 0;
    }
    .container {
      max-width: 600px;
      margin: 40px auto;
      background: #fff;
      padding: 20px;
      box-shadow: 0 0 8px rgba(0,0,0,0.1);
      border-radius: 6px;
    }
    h2 {
      text-align: center;
      margin-bottom: 20px;
      color: #333;
    }
    .qr-section {
      text-align: center;
      margin-bottom: 20px;
    }
    .qr-section img {
      width: 200px;
      height: 200px;
    }
    .payment-info {
      margin-bottom: 20px;
      text-align: center;
    }
    .payment-info p {
      margin: 5px 0;
      font-size: 16px;
      color: #555;
    }
    .form-group {
      margin-bottom: 15px;
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    .form-group label {
      font-weight: bold;
      margin-bottom: 5px;
      color: #333;
    }
    .form-group input {
      padding: 10px;
      width: 80%;
      max-width: 300px;
      border: 1px solid #ccc;
      border-radius: 4px;
    }
    .btn {
      display: inline-block;
      background: #28a745;
      color: #fff;
      padding: 10px 20px;
      text-decoration: none;
      border-radius: 4px;
      margin-top: 10px;
      cursor: pointer;
    }
    .btn:hover {
      background: #218838;
    }
    .note {
      font-size: 14px;
      color: #666;
      text-align: center;
      margin-top: 10px;
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>Easypaisa Payment</h2>
    <div class="qr-section">
      <!-- QR Code Image -->
      <img 
        src="https://i.ibb.co/1qztM2Z/easypaisa-qr-code-demo.png" 
        alt="Easypaisa QR Code"
      />
    </div>
    <div class="payment-info">
      <p><strong>Account Name:</strong> Pervez Masih</p>
      <p><strong>MSISDN (Number):</strong> 03********3</p>
      <p>اس QR کوڈ کو اسکین کریں یا نیچے نمبر پر پیمنٹ بھیجیں۔</p>
    </div>

    <form onsubmit="return handlePayment(event)">
      <div class="form-group">
        <label for="senderNumber">Sender's Mobile Number</label>
        <input 
          type="tel" 
          id="senderNumber" 
          name="senderNumber" 
          placeholder="Enter your mobile number" 
          required
        />
      </div>
      <button type="submit" class="btn">Confirm Payment</button>
    </form>

    <p class="note">نوٹ: پیمنٹ کرنے کے بعد آپ کو SMS کے ذریعے تصدیق موصول ہوگی۔</p>
  </div>

  <script>
    function handlePayment(e) {
      e.preventDefault();
      const number = document.getElementById('senderNumber').value;
      // یہ جگہ اصل Easypaisa API انٹیگریشن کے لیے ہے
      // فی الحال ہم ایک سمپل میسج شو کر دیتے ہیں
      alert('شکریہ! آپ نے نمبر ' + number + ' سے ادائیگی بھیج دی ہے۔');
      // فارم ری سیٹ
      e.target.reset();
      return false;
    }
  </script>
</body>
</html>
