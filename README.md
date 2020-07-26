# html
<!DOCTYPE html>
<html>
<head>
   <title>Web Page</title>
   <style type="text/css">
       table tr:nth-child(even){background-color: lightblue;}
       table tr:nth-child(odd){background-color: red;}
   </style>
</head>
<body style="margin-top: 0px;padding:0px">
   <div id="main" style="width: 100%;display: block;margin-top: 0px;padding: 0px">
       <div id="sidediv" style="width: 20%;background-color: lightblue;height:700px;display: block;margin-top: 0px;float: left">
           <h1 style="color:blue" align="center">My Favourite Links</h3>
           <a href="https://www.instinctme.com">instincme</a><br />
           <a href="https://www.google.com">Google</a><br />
           <a href="https://www.youtube.com">Youtube</a>
       </div>
       <div id="main_content">
           <div id="heading" style="width: 100%;background-image: url('1.jpg');height: 200px">
               <h1 align="center" style="color:blue;font-size: 40px">Welcome to KASIREDDY'S Website</h1>
           </div>
           <div id="tablediv" style="background-color: lightgreen;height: 500px">
                   <br />
                   <h1 align="center" style="color:blue"> My JavaScript Prgramming example</h1>
                   <h2 align="center" style="color: blue">Double Declining Depreciation Table</h3>

                   Enter Property Value : <input type="text" name="prop_value" id="prop_value" /><br /><br />
                   Enrter Property LifeL <input type="text" name="life" id="life" /> <br /><br />
                   <input type="button" onclick="dddt()" value="Show Table" /><br /><br />
                   <div id="table_area">
                   </div>
           </div>
       </div>
   </div>
   <script type="text/javascript">
       function dddt(){
           var prop_value = parseFloat(document.getElementById("prop_value").value);
           var life = parseInt(document.getElementById("life").value);
           var table = "<table border='1' style='border-collapse:collapse'><tr style='background-color:lightgreen'><th>Year</th><th>Value at BeginYr</th><th>Dep During Yr</th><th>Total to EndOfYr</th></tr>";
           var i, val_begin, dep_year, total_end_year=0;
           val_begin = prop_value;
           for(i=1;i<life;i++){
               dep_year = val_begin / life;
               total_end_year+= dep_year;
               table+="<tr><td>"+i+"</td><td>$"+val_begin.toFixed(2)+"</td><td>$"+dep_year.toFixed(2)+"</td><td>$"+total_end_year.toFixed(2)+"</td></tr>";
               val_begin = val_begin - dep_year;
           }
           table+= "<tr><td>"+life+"</td><td>$"+val_begin.toFixed(2)+"</td><td>$"+val_begin.toFixed(2)+"</td><td>$"+prop_value.toFixed(2)+"</td><tr></table>";
           document.getElementById("table_area").innerHTML = table;
       }
   </script>
</body>
</html>
