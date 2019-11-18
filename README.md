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
