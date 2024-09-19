# BTVN-AWD
- Bài tập 1:
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <style type="text/css">
        .square1{
            height: 20px;
            width: 20px;
            float: left;
            border: 1px solid gray;
            margin-left: 5px;
            margin-bottom: 5px;
            background: sliver;

        }
        .square2{
            height: 20px;
            width: 20px;
            float: left;
            border:1px solid gray;
            margin-left: 5px;
            margin-bottom: 5px;
            background: red;
        }
   </style>
<script>
    for (var i=0; i<=5;i++){
        for( var j=0;j<=10;j++){
            if(i%2==0){
                document.write("<div class='square1'></div>");
            }else{
                document.write("<div class='square2'></div>");
            }
        }
            document.write("<div style='clear:both'></div>");
   }

</script>

</body>
</html>
- Bài tập 2:
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bảng Điểm</title>
    <style>
        body {
            background-color: lightgray;
        }

        .container {
            background-color: rgb(118, 113, 113);
            padding: 20px;
            width: 300px;
            margin: 100px auto;
            border: 2px solid rgb(0, 0, 0);
            color: black;
            font-family: Arial, sans-serif;
        }

        h1 {
            color: blue;
            text-align: center;
        }

        label {
            display: block;
            margin-bottom: 5px;
        }

        input[type="number"], select {
            width: 100%;
            padding: 5px;
            margin-bottom: 10px;
        }

        .summary {
            background-color: lightgray;
            width: 100%;
            padding: 5px;
            margin-bottom: 10px;
        }

        .status {
            color: red;
            font-size: 20px;
            text-align: center;
            margin-bottom: 20px;
        }

        .buttons {
            text-align: center;
        }

        button {
            padding: 5px 15px;
            margin: 5px;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>BANG DIEM CUA EM</h1>
    <form onsubmit="calculateSummary(); return false;">
        <label for="semester1">Semester 1:</label>
        <input type="number" id="semester1" min="0" max="10" required>

        <label for="semester2">Semester 2:</label>
        <input type="number" id="semester2" min="0" max="10" required>

        <label for="year">Year:</label>
        <select id="year">
            <option value="1">1</option>
            <option value="2">2</option>
            <option value="3">3</option>
            <option value="4">4</option>
            <option value="5">5</option>
        </select>

        <label for="summary">Summarise:</label>
        <input type="text" id="summary" class="summary" readonly>

        <div class="status" id="status"></div>

        <div class="buttons">
            <button type="submit">OK</button>
            <button type="button" onclick="resetForm()">Cancel</button>
        </div>
    </form>
</div>

<script>
    function calculateSummary() {
        var sem1 = parseFloat(document.getElementById('semester1').value);
        var sem2 = parseFloat(document.getElementById('semester2').value);
        var statusElement = document.getElementById('status');

        
        if (sem1 > 10 || sem2 > 10) {
            statusElement.textContent = "Điểm phải nhỏ hơn hoặc bằng 10!";
            statusElement.style.color = "red";
            document.getElementById('summary').value = '';
        } else {
            var summary = (sem1 + sem2) / 2;
            document.getElementById('summary').value = summary.toFixed(2);

            
            if (summary >= 8.5) {
                statusElement.textContent = "Học sinh giỏi";
                statusElement.style.color = "yellow";
            } else if (summary >= 7 && summary <= 8.4) {
                statusElement.textContent = "Học sinh khá";
                statusElement.style.color = "yellow";
            } else if (summary >= 5.5 && summary <= 6.9) {
                statusElement.textContent = "Học sinh trung bình";
                statusElement.style.color = "yellow";
            } else {
                statusElement.textContent = "Học sinh yếu";
                statusElement.style.color = "yellow";
            }
        }
    }

    function resetForm() {
        document.querySelector('form').reset();
        document.getElementById('summary').value = '';
        document.getElementById('status').textContent = '';
    }
</script>

</body>
</html>
