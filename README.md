# AppScript_Test
Simple function in app script for google sheets

/** 
*Sum all savings
*
*@param {texto} cell to sum across sheets
*@return Saving Sum
*
*@customfunction
*/
function SumSavings() {
  var dir='C11';
  const book= SpreadsheetApp.getActiveSpreadsheet();

  var sheets=book.getSheets();

  var sum=0;
  sheets.forEach(function(sheet){
    sum=sum+Number(sheet.getRange(dir).getValue());
  });
  
  Logger.log(sum)
  return sum;
} 


function onEdit() {
  
  var celdaActiva=SpreadsheetApp.getActiveSpreadsheet().getActiveSheet().getActiveCell();
  SpreadsheetApp.getActiveSpreadsheet
  var filaActiva = celdaActiva.getRow();
  var colActiva = celdaActiva.getColumn();
  var valor = celdaActiva.getValue();

  var ss = SpreadsheetApp.getActiveSpreadsheet();
  var allsheets=ss.getSheets();
  for(var s in allsheets){
    var sheet2 = allsheets[s];
    if(filaActiva===11 && colActiva===3) {
            
            var sheet = ss.getSheetByName('Total Savings');
            

            var dir='C11';
            const book= SpreadsheetApp.getActiveSpreadsheet();

            var sheets=book.getSheets();

            var sum=0;
            sheets.forEach(function(sheet){
              sum=sum+Number(sheet.getRange(dir).getValue());
            });




            sheet2.getRange('C14').setValue(sum);
    // Stop iteration execution if the condition is meet.
  }
  
    
  }

}

