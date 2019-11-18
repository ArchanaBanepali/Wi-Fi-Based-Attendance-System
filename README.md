 #CODE
 
 
 function doGet(e){
  Logger.log(e.parameter);
  return HtmlService.createHtmlOutputFromFile("captive portal");
  }

function userlogin(name){
  var url = "https://docs.google.com/spreadsheets/d/1N21HCVAb7z-PKASbTYDRCk_OuE-q1Te18Y_a9igNLx4/edit#gid=0";
  var ss = SpreadsheetApp.openByUrl(url);
  var ws = ss.getSheetByName("database");
  
  ws.appendRow([name, new Date()]);  
  //Logger.log(name + " user logged in");
  }


#CAPTIVE_PORTAL_CODE


<!DOCTYPE html>
<html>
  <head>
    <base target="_top">
  </head>
  <body>
    
    <h1>Login Page</h1>
    <h2></h2>
    <label>Name:</label><input type="text" id="username">
    <h3></h3>
    <label>Password:</label><input type="text" id="password">
    <h4></h4>
    
    <button id="btn">login</button>
    
    
    
    <script>
    document.getElementById("btn").addEventListener("click",getinfo);
    
    function getinfo(){
    
    var uname = document.getElementById("username").value;
     google.script.run.userlogin(uname);
     document.getElementById("username").value="";
    
    }
    
    
    </script>
  </body>
</html>


