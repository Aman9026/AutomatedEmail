```
function sendEmails() {
  var sheet = SpreadsheetApp.getActiveSheet();
  var startRow = 2; // First row of data to process
  var numRows = 2; // Number of rows to process
  // Fetch the range of cells A2:B3
  var dataRange = sheet.getRange(startRow, 1, numRows, 3);
  // Fetch values for each row in the Range.
     var subject = 'Update on next steps'
  var data = dataRange.getValues();
  for (i in data) {
    var row = data[i];
    var emailAddress = row[0]; // First column
    var name= row[1]; //second column
    var message = 'Hi '+ name + ',' + '\n' + 'First of all, thank you for submitting your interest form for Developer Student Clubs. '+ '\n'+
        'We are very excited to invite you to the next step of DSC core team enrollment,'+
        ' which is an online video conversation (via Google Meet) with a DSC team contact.' + '\n\n'
        'Book your interview slot';
    MailApp.sendEmail(emailAddress, subject, message);
  }
}
```
