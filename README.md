<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>عصائر حسام الطازجة</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      background: linear-gradient(45deg, #ff9a9e, #fad0c4, #fad0c4);
      margin: 0; padding: 0;
      color: #444;
    }
    header {
      background: #ff6f61;
      color: white;
      text-align: center;
      padding: 20px 10px;
      font-size: 2.2em;
      font-weight: bold;
      text-shadow: 1px 1px 2px #a6372b;
    }
    h2.section-title {
      text-align: center;
      color: #ff6f61;
      margin: 40px 0 20px;
      font-weight: bold;
      font-size: 2em;
      text-shadow: 0 0 5px #ff6f61;
    }
    .container {
      max-width: 1100px;
      margin: 0 auto 40px;
      padding: 10px;
      display: flex;
      gap: 25px;
      flex-wrap: wrap;
      justify-content: center;
    }
    .card {
      background: white;
      border-radius: 15px;
      box-shadow: 0 3px 8px rgba(0,0,0,0.2);
      width: 220px;
      text-align: center;
      padding: 15px;
      transition: transform 0.2s ease;
      min-height: 260px;
      display: flex;
      flex-direction: column;
      justify-content: center;
    }
    .card:hover {
      transform: scale(1.05);
    }
    /* حذفت الصور */
    .card h3 {
      margin: 10px 0 8px;
      color: #e34a4a;
      font-size: 1.3em;
      font-weight: 900;
    }
    .card p {
      font-weight: 600;
      color: #444;
      margin-bottom: 15px;
      font-size: 1em;
      line-height: 1.3;
      flex-grow: 1;
    }
    .card button {
      background: #ff6f61;
      border: none;
      color: white;
      padding: 10px 16px;
      border-radius: 10px;
      cursor: pointer;
      font-weight: bold;
      font-size: 1em;
      box-shadow: 0 2px 5px rgba(255,111,97,0.6);
      transition: background-color 0.3s ease;
      align-self: center;
      width: 90%;
    }
    .card button:hover {
      background-color: #e04c4c;
    }

    /* نموذج الطلب */
    #overlay {
      display: none;
      position: fixed;
      top: 0; left: 0; right:0; bottom:0;
      background: rgba(0,0,0,0.7);
      z-index: 999;
    }
    #orderForm {
      display: none;
      position: fixed;
      top: 50%;
      left: 50%;
      width: 350px;
      padding: 25px 30px;
      background: white;
      border-radius: 15px;
      box-shadow: 0 3px 15px rgba(0,0,0,0.4);
      transform: translate(-50%, -50%);
      z-index: 1000;
      direction: rtl;
    }
    #orderForm h2 {
      color: #ff6f61;
      margin-bottom: 20px;
      text-align: center;
      font-weight: 900;
      letter-spacing: 1px;
    }
    #orderForm label {
      display: block;
      margin: 12px 0 6px;
      font-weight: bold;
      color: #333;
    }
    #orderForm select, #orderForm input {
      width: 100%;
      padding: 10px 12px;
      border: 1px solid #ccc;
      border-radius: 10px;
      font-size: 1em;
      transition: border-color 0.3s ease;
    }
    #orderForm select:focus, #orderForm input:focus {
      border-color: #ff6f61;
      outline: none;
    }
    #orderForm button[type="submit"] {
      margin-top: 20px;
      background: #ff6f61;
      color: white;
      border: none;
      padding: 14px;
      font-weight: bold;
      border-radius: 15px;
      cursor: pointer;
      width: 100%;
      box-shadow: 0 3px 8px rgba(255,111,97,0.7);
      font-size: 1.1em;
      transition: background-color 0.3s ease;
    }
    #orderForm button[type="submit"]:hover {
      background-color: #e04c4c;
    }
    #orderForm button.cancelBtn {
      background: #ccc;
      color: #444;
      margin-top: 10px;
      width: 100%;
      border-radius: 15px;
      font-weight: bold;
      padding: 12px;
    }
    #orderForm button.cancelBtn:hover {
      background: #aaa;
    }

  </style>
</head>
<body>

<header>عصائر حسام الطازجة</header>

<h2 class="section-title">العصائر الطازجة 🍹</h2>
<div class="container">

  <div class="card">
    <h3>عصير تفاح 🍎</h3>
    <p>استمتع بأجود عصير تفاح طازج 100%، غني بالنكهات الطبيعية المنعشة والمنشطة 💪🍏.</p>
    <button onclick="openForm('juice', 'عصير تفاح')">اطلب الآن</button>
  </div>

  <div class="card">
    <h3>عصير برتقال 🍊</h3>
    <p>نكهة برتقال طبيعية مليئة بفيتامين سي الحيوي لتعزيز صحتك ونشاطك اليومي ☀️🍹.</p>
    <button onclick="openForm('juice', 'عصير برتقال')">اطلب الآن</button>
  </div>

  <div class="card">
    <h3>عصير كيوي 🥝</h3>
    <p>عصير كيوي فريد من نوعه بطعمه الحامضي المنعش والمليء بالمركبات المغذية 🌿🍃.</p>
    <button onclick="openForm('juice', 'عصير كيوي')">اطلب الآن</button>
  </div>

  <div class="card">
    <h3>عصير أناناس 🍍</h3>
    <p>طعم استوائي لذيذ مع فوائد إنزيمات الهضم الطبيعية لجسم صحي وحيوي 🌞🍍.</p>
    <button onclick="openForm('juice', 'عصير أناناس')">اطلب الآن</button>
  </div>

  <div class="card">
    <h3>عصير جوافة 🍈</h3>
    <p>نكهة جوافة غنية بالفيتامينات والألياف، تمنحك انتعاشًا وطاقة متجددة 🌟🥤.</p>
    <button onclick="openForm('juice', 'عصير جوافة')">اطلب الآن</button>
  </div>

  <div class="card">
    <h3>عصير رمان ❤️</h3>
    <p>مليء بمضادات الأكسدة التي تعزز المناعة وتحافظ على شباب بشرتك 🍷✨.</p>
    <button onclick="openForm('juice', 'عصير رمان')">اطلب الآن</button>
  </div>

  <div class="card">
    <h3>عصير مانجو 🥭</h3>
    <p>نكهة مانجو غنية وطبيعية تعطيك شعور الصيف والانتعاش الحقيقي 🌞🍹.</p>
    <button onclick="openForm('juice', 'عصير مانجو')">اطلب الآن</button>
  </div>

  <div class="card">
    <h3>عصير فراولة 🍓</h3>
    <p>حلاوة طبيعية مع لمسة منعشة من الفراولة الطازجة والصحية 🍓💖.</p>
    <button onclick="openForm('juice', 'عصير فراولة')">اطلب الآن</button>
  </div>

  <div class="card">
    <h3>عصير ليمون 🍋</h3>
    <p>انتعاش طبيعي وحمضي لطيف يحفز نشاطك ويعزز مناعتك 🌿🍋.</p>
    <button onclick="openForm('juice', 'عصير ليمون')">اطلب الآن</button>
  </div>

  <div class="card">
    <h3>عصير بطيخ 🍉</h3>
    <p>مشروب صيفي منعش يروي عطشك بنكهة البطيخ الحلوة الطبيعية 🌞🍉.</p>
    <button onclick="openForm('juice', 'عصير بطيخ')">اطلب الآن</button>
  </div>

</div>

<h2 class="section-title">آيس كريم حسام 🍦</h2>
<div class="container">

  <div class="card">
    <h3>آيس كريم فانيليا 🍨</h3>
    <p>طعم فانيليا ناعم وكريمي يذوب في فمك ليمنحك لحظات من السعادة والراحة 🌼🍦.</p>
    <button onclick="openForm('icecream', 'آيس كريم فانيليا')">اطلب الآن</button>
  </div>

  <div class="card">
    <h3>آيس كريم شوكولاتة 🍫</h3>
    <p>نكهة شوكولاتة فاخرة وغنية تعزز مزاجك وتمنحك دفء الحلاوة والانتعاش 🍫💖.</p>
    <button onclick="openForm('icecream', 'آيس كريم شوكولاتة')">اطلب الآن</button>
  </div>

  <div class="card">
    <h3>آيس كريم فراولة 🍓</h3>
    <p>مذاق فراولة طبيعي مع ملمس كريمي سلس يداعب حواسك ويبهج يومك 🍓✨.</p>
    <button onclick="openForm('icecream', 'آيس كريم فراولة')">اطلب الآن</button>
  </div>

  <div class="card">
    <h3>آيس كريم نعناع 🌿</h3>
    <p>انتعاش النعناع المنعش مع قوام كريمي ينعش مزاجك وينعش يومك 🍃❄️.</p>
    <button onclick="openForm('icecream', 'آيس كريم نعناع')">اطلب الآن</button>
  </div>

  <div class="card">
    <h3>آيس كريم قهوة ☕</h3>
    <p>مزيج من القهوة الغنية والآيس كريم الناعم يمنحك دفعة طاقة وانتعاش مميزة ☕🔥.</p>
    <button onclick="openForm('icecream', 'آيس كريم قهوة')">اطلب الآن</button>
  </div>

</div>

<!-- نموذج الطلب -->
<div id="overlay"></div>
<form id="orderForm" onsubmit="submitOrder(event)">
  <h2 id="formTitle">طلب العصير</h2>

  <label for="customerName">الاسم الكامل:</label>
  <input type="text" id="customerName" placeholder="اكتب اسمك هنا" required />

  <label for="sizeSelect">اختر الحجم:</label>
  <select id="sizeSelect" required></select>

  <!-- إضافة اختيار طريقة الدفع -->
  <label for="paymentMethod">طريقة الدفع:</label>
  <select id="paymentMethod" required>
    <option value="(كاش-شيكة)الدفع عند الاستلام">(كاش-شيكة)الدفع عند الاستلام</option>
    <option value="الدفع الإلكتروني">الدفع الإلكتروني</option>
    <option value="التحويل البنكي">التحويل البنكي
    </option>
  </select>

  <p style="margin-top: 15px; font-weight:bold; text-align:center; color:#ff6f61;">
    رقم التواصل: 966506680706 (واتساب فقط)
  </p>

  <button type="submit">إرسال الطلب</button>
  <button type="button" class="cancelBtn" onclick="closeForm()">إلغاء</button>
</form>

<script>
  let currentProductType = "";
  let currentProductName = "";

  // الاحجام لكل نوع منتج
  const sizes = {
    juice: [
      {label: "صغير (7ريال)", value: "صغير (7ريال)"},
      {label: "متوسط (10ريال)", value: "متوسط (10ريال)"},
      {label: "كبير (13ريال)", value: "كبير (13ريال)"}
    ],
    icecream: [
      {label: "(5) صغير", value: "(5) صغير"},
      {label: "(10) متوسط", value: "(10) متوسط"},
      {label: "(15) كبير", value: "(15)كبير"}
    ]
  };

  function openForm(type, name) {
    currentProductType = type;
    currentProductName = name;

    document.getElementById("formTitle").textContent = `طلب ${name}`;
    const sizeSelect = document.getElementById("sizeSelect");
    sizeSelect.innerHTML = "";

    sizes[type].forEach(size => {
      const option = document.createElement("option");
      option.value = size.value;
      option.textContent = size.label;
      sizeSelect.appendChild(option);
    });

    document.getElementById("customerName").value = "";
    document.getElementById("paymentMethod").value = "الدفع عند الاستلام";

    document.getElementById("overlay").style.display = "block";
    document.getElementById("orderForm").style.display = "block";
  }

  function closeForm() {
    document.getElementById("overlay").style.display = "none";
    document.getElementById("orderForm").style.display = "none";
  }

  function submitOrder(event) {
    event.preventDefault();

    const name = document.getElementById("customerName").value.trim();
    const size = document.getElementById("sizeSelect").value;
    const payment = document.getElementById("paymentMethod").value;

    if (!name) {
      alert("الرجاء إدخال الاسم الثلاثي.");
      return;
    }

    // صياغة رسالة الطلب للواتساب
    const message =
      `السلام عليكم، أود طلب ${currentProductName} بحجم ${size}.` +
      `\nالاسم: ${name}` +
      `\nطريقة الدفع: ${payment}` +
      `\n\nشكراً لكم.`;

    const encodedMessage = encodeURIComponent(message);

    // رقم واتساب بدون +
    const phone = "966506680706";

    // فتح رابط الواتساب في نافذة جديدة
    window.open(`https://wa.me/${phone}?text=${encodedMessage}`, "_blank");

    closeForm();
  }
</script>

</body>
</html>
