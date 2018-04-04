# weightconverter
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" 
    content="ie=edge">
   <link rel="stylesheet"
    href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css"
    integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm"
    crossorigin="anonymous">
<style>
    body
    {margin-top: top 70px;
        background:rgb(180, 64, 64)
        
        

     }
</style>
   
    <title>WEIGHTCONVERTER</title>
</head>
<body>
    <div class="container">
        <div class="row">
            <div class="col-md-6 offset-md-3">
                <h1 class="display-4 text-center mb-4">Weight Converter</h1>
                <form>
                    <div class="form-group">
                        <select id="inputSelector" class="form-control form-control-lg mb-3">
                            <option class="option" value="Select unit" selected>Select unit</option>
                            <option class="option" id="lbsSelector" value="pounds">Pounds</option>
                            <option class="option" id="kgSelector" value="Kg">Kilograms</option>
                            <option class="option" id="gramsSelector" value="grams">Grams</option>
                            <option class="option" id="ozSelector" value="oz">Ounces</option>
                        </select>
                        <input id="userInput" type="number" class="form-control form-control-lg mb-5" placeholder="Enter value...">
                    </div>
                </form>
                <div id="output">
                    <div class="block mb-2" id="gramsBlock">
                        <h4>Grams:</h4>
                        <div id="gramsOutput"></div>
                    </div>
                    <div class="block mb-2" id="kgBlock">
                        <h4>Kilograms:</h4>
                        <div id="kgOutput"></div>
                    </div>
                    <div class="block mb-2" id="ozBlock">
                        <h4>Ounces:</h4>
                        <div id="ozOutput"></div>
                    </div>
                    <div class="block mb-2" id="lbsBlock">
                        <h4>Pounds:</h4>
                        <div id="lbsOutput"></div>
                    </div>
                </div>
            </div>
        </div>
    </div>

  <script>
     window.onload = function() {

var select = document.getElementById("inputSelector");
select.addEventListener("change", showOutput);

function clear() {
    let inputVal = document.getElementById('userInput');
    inputVal.value = "";
    document.getElementById("lbsBlock").style.display = "none";
    document.getElementById("kgBlock").style.display = "none";
    document.getElementById("ozBlock").style.display = "none";
    document.getElementById("gramsBlock").style.display = "none";
}

function round(val) {
    return Math.round(val)
}

function showOutput(e) {
    clear();
    let val = e.target.value;
    if (val == "pounds") {

        document.getElementById("userInput").addEventListener("input", function(e) {
            let lbs = e.target.value;

            document.getElementById("lbsBlock").style.display = "none";
            document.getElementById("kgBlock").style.display = "block";
            document.getElementById("ozBlock").style.display = "block";
            document.getElementById("gramsBlock").style.display = "block";
            document.getElementById("gramsOutput").innerHTML = round(lbs / 0.0022046);
            document.getElementById("kgOutput").innerHTML = round(lbs / 2.2046);
            document.getElementById("ozOutput").innerHTML = round(lbs * 16);
        });
    }


    if (val == "Kg") {

        document.getElementById("userInput").addEventListener("input", function(e) {
            let kg = e.target.value;

            document.getElementById("kgBlock").style.display = "none";
            document.getElementById("lbsBlock").style.display = "block";
            document.getElementById("ozBlock").style.display = "block";
            document.getElementById("gramsBlock").style.display = "block";
            document.getElementById("gramsOutput").innerHTML = round(kg * 1000);
            document.getElementById("lbsOutput").innerHTML = round(kg * 2.2046);
            document.getElementById("ozOutput").innerHTML = round(kg * 32.27);

        });

    }
    if (val == "grams") {

        document.getElementById("userInput").addEventListener("input", function(e) {
            let grams = e.target.value;

            document.getElementById("gramsBlock").style.display = "none";
            document.getElementById("kgBlock").style.display = "block";
            document.getElementById("lbsBlock").style.display = "block";
            document.getElementById("ozBlock").style.display = "block";
            document.getElementById("kgOutput").innerHTML = round(grams / 1000);
            document.getElementById("lbsOutput").innerHTML = round(grams / 453.59237);
            document.getElementById("ozOutput").innerHTML = round(grams * 0.035274);
        });
    }
    if (val == "oz") {

        document.getElementById("userInput").addEventListener("input", function(e) {
            let oz = e.target.value;

            document.getElementById("ozBlock").style.display = "none";
            document.getElementById("gramsBlock").style.display = "block";
            document.getElementById("kgBlock").style.display = "block";
            document.getElementById("lbsBlock").style.display = "block";
            document.getElementById("kgOutput").innerHTML = round(oz * 0.02834);
            document.getElementById("lbsOutput").innerHTML = round(oz / 16);
            document.getElementById("gramsOutput").innerHTML = round(oz * 28.35);
        });

    }
}
}
  </script>
</body>

</html>
