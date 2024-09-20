<html lang="en-US">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Calculator</title>
<script>
    function Nhan() {
        var a = parseFloat(document.getElementById("txtA").value);
        var b = parseFloat(document.getElementById("txtB").value);
        document.getElementById("txtKQnhan").value = a * b;
    }

    function Cong() {
        var c = parseFloat(document.getElementById("txtC").value);
        var d = parseFloat(document.getElementById("txtD").value);
        document.getElementById("txtKQcong").value = c + d;
    }

    function Tru() {
        var e = parseFloat(document.getElementById("txtE").value);
        var f = parseFloat(document.getElementById("txtF").value);
        document.getElementById("txtKQtru").value = e - f;
    }

    function Chia() {
        var g = parseFloat(document.getElementById("txtG").value);
        var h = parseFloat(document.getElementById("txtH").value);
        document.getElementById("txtKQchia").value = g / h;
    }

    function giaiPhuongTrinhBacNhat() {
        var j = parseFloat(document.getElementById("txtJ").value);
        var k = parseFloat(document.getElementById("txtK").value);

        var result = document.getElementById("result");
        if (j === 0) {
            if (k === 0) {
                result.textContent = "Phương trình có vô số nghiệm";
            } else {
                result.textContent = "Phương trình vô nghiệm";
            }
        } else {
            var x = -k / j;
            result.textContent = "Nghiệm của phương trình là x = " + x;
        }
    }
    function soNgayTrongThang(thang, nam) {
        if (thang === 2) {
            if ((nam % 4 === 0 && nam % 100 !== 0) || nam % 400 === 0) {
                return 29; // Năm nhuận
            } else {
                return 28; // Năm không nhuận
            }
        } else if ([4, 6, 9, 11].includes(thang)) {
            return 30;
        } else {
            return 31;
        }
    }

    function tinhSoNgay() {
        var thang = parseInt(document.getElementById("thang").value);
        var nam = parseInt(document.getElementById("nam").value);

        var soNgay = soNgayTrongThang(thang, nam);
        document.getElementById("ketqua").textContent = "Tháng " + thang + " năm " + nam + " có " + soNgay + " ngày.";
    }
</script>
</head>
<body>
    <p>JavaScript</p>
    <p>Tác dụng: làm trang web linh hoạt và có tương tác</p>
    <p>Các phép toán cơ bản</p>

    <p>Phép cộng: 
        <input type="text" id="txtC" name="txtC" size="13">&nbsp; +&nbsp; 
        <input type="text" id="txtD" name="txtD" size="14">&nbsp;
        <input type="button" value=" = " onclick="Cong()">
        <input type="text" id="txtKQcong" name="T6" size="16"> 
    </p>
    <p>Phép trừ: 
        <input type="text" id="txtE" name="txtE" size="13">&nbsp; -&nbsp; 
        <input type="text" id="txtF" name="txtF" size="14">&nbsp;
        <input type="button" value=" = " onclick="Tru()">
        <input type="text" id="txtKQtru" name="T6" size="16"> 
    </p>
    <p>Phép nhân: 
        <input type="text" id="txtA" name="txtA" size="13">&nbsp; x&nbsp; 
        <input type="text" id="txtB" name="txtB" size="14">&nbsp;
        <input type="button" value=" = " onclick="Nhan()">
        <input type="text" id="txtKQnhan" name="T6" size="16"> 
    </p>
    <p>Phép chia: 
        <input type="text" id="txtG" name="txtG" size="13">&nbsp; /&nbsp; 
        <input type="text" id="txtH" name="txtH" size="14">&nbsp;
        <input type="button" value=" = " onclick="Chia()">
        <input type="text" id="txtKQchia" name="T6" size="16"> 
    </p>

    <p>Giải phương trình bậc nhất: ax + b = 0</p>
    <p>Nhập giá trị của a và b để giải phương trình:</p>
    <label for="txtJ">Nhập giá trị của a:</label>
    <input type="text" id="txtJ"><br><br>
    <label for="txtK">Nhập giá trị của b:</label>
    <input type="text" id="txtK"><br><br>
    <button onclick="giaiPhuongTrinhBacNhat()">Giải phương trình</button><br><br>
    <p id="result"></p>
    <label for="thang">Tháng:</label>
    <input type="number" id="thang" min="1" max="12"><br><br>

    <label for="nam">Năm:</label>
    <input type="number" id="nam" min="1900"><br><br>

    <button onclick="tinhSoNgay()">Tính số ngày</button><br><br>

    <p id="ketqua"></p>
</body>
</html>
