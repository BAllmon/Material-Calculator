<html lang="en">


<head>
	<title> Parts Calculator: </title>
</head>
        <script>
		//function to calculate the number of pieces needed
		function calcNum(){
			var firstQ = +document.getElementById("firstQuantity").value;
			var firstS = +document.getElementById("firstSize").value;
			var secondQ = +document.getElementById("secondQuantity").value;
			var secondS = +document.getElementById("secondSize").value;
			var thirdQ = +document.getElementById("thirdQuantity").value;
			var thirdS = +document.getElementById("thirdSize").value;
			var fourthQ = +document.getElementById("fourthQuantity").value;
			var fourthS = +document.getElementById("fourthSize").value;	
			var fifthQ = +document.getElementById("fifthQuantity").value;
			var fifthS = +document.getElementById("fifthSize").value;
			var sixthQ = +document.getElementById("sixthQuantity").value;
			var sixthS = +document.getElementById("sixthSize").value;
			var seventhQ = +document.getElementById("seventhQuantity").value;
			var seventhS = +document.getElementById("seventhSize").value;
			var eighthQ = +document.getElementById("eighthQuantity").value;
			var eighthS = +document.getElementById("eighthSize").value;
			var ninthQ = +document.getElementById("ninthQuantity").value;
			var ninthS = +document.getElementById("ninthSize").value;
			var tenthQ = +document.getElementById("tenthQuantity").value;
			var tenthS = +document.getElementById("tenthSize").value;
			var purch = (+document.getElementById("purchaseSize").value)*12;
			var valArray=[];
		
			if(firstQ!=0 && firstS!=0){count(firstQ,firstS,purch,valArray);}
			if(secondQ!=0 && secondS!=0){count(secondQ,secondS,purch,valArray);}
			if(thirdQ!=0 && thirdS!=0){count(thirdQ,thirdS,purch,valArray);}
			if(fourthQ!=0 && fourthS!=0){count(fourthQ,fourthS,purch,valArray);}
			if(fifthQ!=0 && fifthS!=0){count(fifthQ,fifthS,purch,valArray);}
			if(sixthQ!=0 && sixthS!=0){count(sixthQ,sixthS,purch,valArray);}
			if(seventhQ!=0 && seventhS!=0){count(seventhQ,seventhS,purch,valArray);}
			if(eighthQ!=0 && eighthS!=0){count(eighthQ,eighthS,purch,valArray);}
			if(ninthQ!=0 && ninthS!=0){count(ninthQ,ninthS,purch,valArray);}
			if(tenthQ!=0 && tenthS!=0){count(tenthQ,tenthS,purch,valArray);}			
			return valArray.length;
		}
		
		function displayTotal() {
 			document.getElementById("demo").innerHTML = calcNum();
		}
		function count(Q,S,purch, array){
			var k=0;
			for(num=0; num<array.length; num++){
				k=checkExtra(array[num], Q, S, k,array, num);
			}
			while(k!=Q){
				k=checkAll(purch, Q, S, k, array); 
			}
		}

		function checkAll(value, Q, S, k, array){
			while(value>=0 && k<=Q){
				k++;
				value-=S;
			}
		array.push(value+S);
		return k-1;
		}

		function checkExtra(value, Q, S, k, array, num){
			while(value>=0 && k<=Q){
				k++;
				value-=S;
			}
		array[num]=(value+S);
		return k-1;
		}

	</script>

  <body>
      <div class="form">
	<label for="material"> Type of Material:</label>
  	<input type="text" id="material" name="material">
	<br>
	<label for="firstQuantity"> First Part Quantity:</label>
  	<input type="number" id="firstQuantity" name="firstQuantity">
	<br>
	<label for="firstSize"> First Part Size:</label>
  	<input type="number" id="firstSize" name="firstSize">
	<br>
	<label for="secondQuantity"> Second Part Quantity:</label>
  	<input type="number" id="secondQuantity" name="secondQuantity">
	<br>
	<label for="secondSize"> Second Part Size:</label>
  	<input type="number" id="secondSize" name="secondSize">
	<br>
	<label for="thirdQuantity"> Third Part Quantity:</label>
  	<input type="number" id="thirdQuantity" name="thirdQuantity">
	<br>
	<label for="thirdSize"> Third Part Size:</label>
  	<input type="number" id="thirdSize" name="thirdSize">
	<br>
	<label for="fourthQuantity"> Fourth Part Quantity:</label>
  	<input type="number" id="fourthQuantity" name="fourthQuantity">
	<br>
	<label for="fourthSize"> Fourth Part Size:</label>
  	<input type="number" id="fourthSize" name="fourthSize">
	<br>
	<label for="fifthQuantity"> Fifth Part Quantity:</label>
  	<input type="number" id="fifthQuantity" name="fifthQuantity">
	<br>
	<label for="fifthSize"> Fifth Part Size:</label>
  	<input type="number" id="fifthSize" name="fifthSize">
	<br>
	<label for="sixthQuantity"> Sixth Part Quantity:</label>
  	<input type="number" id="sixthQuantity" name="sixthQuantity">
	<br>
	<label for="sixthSize"> Sixth Part Size:</label>
  	<input type="number" id="sixthSize" name="sixthSize">
	<br>
	<label for="seventhQuantity"> Seventh Part Quantity:</label>
  	<input type="number" id="seventhQuantity" name="seventhQuantity">
	<br>
	<label for="seventhSize"> Seventh Part Size:</label>
  	<input type="number" id="seventhSize" name="seventhSize">
	<br>
	<label for="eighthQuantity"> Eighth Part Quantity:</label>
  	<input type="number" id="eighthQuantity" name="eighthQuantity">
	<br>
	<label for="eighthSize"> Eighth Part Size:</label>
  	<input type="number" id="eighthSize" name="eighthSize">
	<br>
	<label for="ninthQuantity"> Ninth Part Quantity:</label>
  	<input type="number" id="ninthQuantity" name="ninthQuantity">
	<br>
	<label for="ninthSize"> Ninth Part Size:</label>
  	<input type="number" id="ninthSize" name="ninthSize">
	<br>
	<label for="tenthQuantity"> Tenth Part Quantity:</label>
  	<input type="number" id="tenthQuantity" name="tenthQuantity">
	<br>
	<label for="tenthSize"> Tenth Part Size:</label>
  	<input type="number" id="tenthSize" name="tenthSize">
	<br>
	<label for="purchaseSize"> Purchased Size in Feet:</label>
  	<input type="number" id="purchaseSize" name="purchaseSize">
	<br>
	<button onclick="displayTotal()"> Calculate  </button>
      </div>

	<p id="demo"></p>

    </body>
</html>

<style type="text/css">
	.form {
		margin: 10;
		width: 210px;
	}

	.form label{
		display: inline;
		text-align: left;
		float: left;
	}

	.form input{
		display: inline-block;
		text-align: left;
		float: right;
	}
</style>
