<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BMR Calculator</title>

    <style>
        h1 {
            font-family:'Times New Roman', Times, serif;
            font-weight: bold;
            text-align: center;
            color: rgb(93, 185, 222);
        }
        .container {
            width: 600px;
            height: 300px;
            margin: auto;
            border-radius: 8px;
            display: flex;               
            justify-content: center;     
            align-items: center;         
            background-color: rgb(93, 185, 222);
            padding: 10px;
            border: 2px solid black;
        }
        .notice{
            font-size: 30px;
            text-decoration: underline;
            font-family: 'Last Ninja', Impact, fantasy;
            color: black;
        }
        form span{
            display: inline-block;
            width: 40px;
            font-size: 16px;
            text-align: right;
            margin-right: 10px;
            font-weight: bold;
            font-family: 'Times New Roman', Times, serif;
            color:black;
        }

        input, select {
            margin-bottom: 10px;
            width: 150px;
            height: 20px;
            border-radius: 3px;
        }
        button {
            width: 100px;
            height: 30px;
            background-color: plum;
            cursor: pointer;
            font-weight: bold;
        }
        .result { 
            font-family:'Times New Roman', Times, serif;
            font-weight: bold;
            text-align: center;
        }
        .box {
            width: 400px;
            height: 50px;
            margin: auto;
            border-radius: 8px;
            background-color: rgb(93, 185, 222);
            padding: 10px;
            border: 2px solid black;
        }
        p {
            display: flex;               
            justify-content: center;     
            align-items: center;
            font-family: 'Times New Roman', Times, serif;
            font-weight: bold;
        }
        .gender {
            width: 200px;
            height: 50px;
            display: flex;               
            justify-content: center;     
            align-items: center;
        }
    </style>
</head>
<body>
    <h1>What is your BMR(Basal Metabolic Rate)?</h1>
    <div class="container">
    <div class="notice">PLEASE ENTER YOUR INFORMATION.</div>
        <form>
            <span>HEIGHT:</span> <input type="number" id="height"><br/>
            <span>WEIGHT:</span> <input type="number" id="weight"><br/>
            <span>AGE:</span> <input type="number" id="age"><br/>
            <span>GENDER:</span><br/>
                <select id="gender">
                <option value="">SELECT GENDER.</option>
                <option value="male">MALE</option>
                <option value="female">FEMALE</option>
            </select><br/>
            <br>
            <button type="button" onclick="calculate()">CALCULATE</button> 
        </form>
    </div>
    <div class="box">
    <p id="result">
        <script>
            function calculate() {
                const height = document.getElementById("height").value;
                const weight = document.getElementById("weight").value;
                const age = document.getElementById("age").value;
                const gender = document.getElementById("gender").value;

                let bmr;
                
                if(gender === "male") {
                    bmr = 10 * weight + 6.25 * height - 5 * age + 5;
                } else {
                    bmr = 10 * weight + 6.25 * height - 5 * age - 161;
                }

                document.getElementById("result").innerText =
                    "RESULT: " + Math.round(bmr) + " kcal";
            }
        </script>
    </p>
    </div>
</body>
</html>
