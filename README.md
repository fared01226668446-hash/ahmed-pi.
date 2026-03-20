<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تطبيق الفريد للخرسانة - 6 أكتوبر</title>
    <style>
        body { font-family: 'Arial', sans-serif; background-color: #1a1a1a; color: white; text-align: center; padding: 20px; }
        .container { background: #2d2d2d; padding: 25px; border-radius: 20px; border: 2px solid #690096; max-width: 450px; margin: auto; }
        h1 { color: #ff6600; margin-bottom: 5px; }
        .info { color: #bbb; font-size: 14px; margin-bottom: 20px; }
        select, input { width: 100%; padding: 12px; margin: 10px 0; border-radius: 10px; border: none; font-size: 16px; }
        .result-box { background: #3d3d3d; padding: 15px; border-radius: 10px; margin: 20px 0; border: 1px dashed #690096; }
        .pi-price { color: #690096; font-size: 26px; font-weight: bold; display: block; }
        .btn-order { background: #690096; color: white; padding: 15px; width: 100%; border: none; border-radius: 10px; font-size: 18px; font-weight: bold; cursor: pointer; }
    </style>
</head>
<body>

<div class="container">
    <h1>مكتب الفريد للخدمات 🏗️</h1>
    <p class="info">توريد خرسانة جاهزة - 6 أكتوبر والشيخ زايد</p>
    
    <label>منطقة التوريد:</label>
    <select id="area" onchange="calculate()">
        <option value="1">الشيخ زايد</option>
        <option value="1.02">6 أكتوبر (المركز)</option>
        <option value="1.05">حدائق أكتوبر</option>
        <option value="1.1">أكتوبر الجديدة</option>
    </select>

    <label>الكمية المطلوبة (متر مكعب):</label>
    <input type="number" id="qty" placeholder="مثلاً: 50" oninput="calculate()">

    <div class="result-box">
        <p>الإجمالي بعملة Pi:</p>
        <span id="res" class="pi-price">0.00000000 Pi</span>
        <small>سعر التوافق المعتمد: $314,159</small>
    </div>

    <button class="btn-order" onclick="alert('جاري التوصيل بمحفظة Pi... يرجى الانتظار')">تأكيد الطلب والدفع بـ Pi</button>
</div>

<script>
    function calculate() {
        const GCV = 314159;
        const EGP_USD = 50; 
        const BASE_PRICE = 2100; // سعر المتر الوسطي في أكتوبر
        
        let q = document.getElementById('qty').value;
        let a = document.getElementById('area').value;
        
        if(q > 0) {
            let totalPi = ((q * BASE_PRICE * a) / EGP_USD) / GCV;
            document.getElementById('res').innerText = totalPi.toFixed(8) + " Pi";
        } else {
            document.getElementById('res').innerText = "0.00000000 Pi";
        }
    }
</script>

</body>
</html>
