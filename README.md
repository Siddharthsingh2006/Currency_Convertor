<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Currency Convertor</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.13.1/font/bootstrap-icons.min.css">
    <style>
        body{
            background-color: black;
        }
        #Currency{
            width: 300px;
            height: 250px;
            border: 1px solid;
            margin: 120px auto;
            align-items: center;
            text-align: center;
            background-color: white;
            border-radius: 25px;
        }
        #child2{
            height: 30px;
            width: 250px;
            border: 1px solid;
            margin: auto;
            margin-bottom: 20px;
        }
        #child3{
            height: 30px;
            width: 250px;
            border: 1px solid;
            margin: 20px auto;
        }
        input{
            border: none;
            outline: none;
        }
        .selectcurr{
            border-radius: 15px;
            margin-top: 5px;
        }
        .selectcurr{
            border-radius: 15px;
            margin-top: 5px;
        }
        #button{
            height: 40px;
            width: 40px;
            border-radius: 20px;
            background-color: grey;
        }
    </style>
</head>

<body>

    <div id="Currency">
        <h1>Currency Convertor</h1>
        <div class="parent" id="child2">
            <input type="number" id="inp1">
            <select name="" id="selectcurr" class="selectcurr">
                <option value="USD">USD</option>
                <option value="INR">INR</option>
                <option value="GBP">GBP</option>
                <option value="EUR">EUR</option>
                <option value="YUAN">YAN</option>
                <option value="AUD">AUD</option>
                <option value="CAD">CAD</option>
                <option value="OMR">OMR</option>
                <option value="JPY">JPY</option>
            </select>
        </div>
        <button onclick="convert()" id="button"><i class="bi bi-arrow-down-up"></i></button>
        <div class="parent" id="child3">
            <input type="number" name="" id="res">
            <select name="" id="tocurrency" class="selectcurr">
                <option value="USD">USD</option>
                <option value="INR">INR</option>
                <option value="GBP">GBP</option>
                <option value="EUR">EUR</option>
                <option value="YUAN">YAN</option>
                <option value="AUD">AUD</option>
                <option value="CAD">CAD</option>
                <option value="OMR">OMR</option>
                <option value="JPY">JPY</option>
            </select>
        </div>
    </div>

    <script>

        async function convert()
        {
            let amount = document.getElementById("inp1").value;
            let from = document.getElementById("selectcurr").value
            let to = document.getElementById("tocurrency").value
            let apiKey = '81f55a577f0a6eedda9b618e9f96b258'

            let data = await fetch(`https://api.exchangerate.host/convert?from=${from}&to=${to}&amount=${amount}&access_key=${apiKey}`)
            


            console.log(amount);
            console.log(from);
            console.log(to);
            
            console.log(data);

            let result = await data.json();
            
            console.log(result);

            document.getElementById("res").value=`${result.result}`;
            
        }

    </script>

</body>

</html>
