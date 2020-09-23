<div align="center">

## How to use the DataReader \(recordset\)


</div>

### Description

shows you how to use a SqlDataReader
 
### More Info
 
sql statment

SqlDataReader


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[DrDave](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/drdave.md)
**Level**          |Beginner
**User Rating**    |3.7 (11 globes from 3 users)
**Compatibility**  |VB\.NET, ASP\.NET
**Category**       |[Databases](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/databases__10-5.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/drdave-how-to-use-the-datareader-recordset__10-826/archive/master.zip)





### Source Code

```
How to use a System.Data.SqlClient.SqlDataReader
I have inserted ... at the begining of each line so that it is readable...
.
.
.' I Used the frmMain Load sub as an example.
.
.Private Sub frmMain_Load(ByVal Sender As Object, ByVal e As EventArgs) Handles MyBase.load
'Dim all the needed vars
....Dim DR As System.Data.SqlClient.SqlDataReader
....Dim strSQL As String = "SELECT * FROM Users"
....Dim SqlConn As new System.Data.SqlClient.SqlConnection("Persist Security Info=False;Data Source=localhost;Initial Catalog=MyDb;User ID=sa;Password=;")
'Open the Database
....SqlConn.open()
....Dim SqlComm As new System.Data.SqlClient.SqlCommand(strSQL, SqlConn)
'Execute the reader
....DR = SqlComm.ExecuteReader
'Loop through the records and add the "UserName" to a text box
....Do While DR.Read()
.......txtUserNames.Text &= VbCrLf & DR.Item("UserName")
....Loop
'Close everything
....DR.Close()
....SqlConn.Close()
....SqlComm.Dispose()
....SqlConn.Dispose()
'setting the values to nothing is not required but I like to do it anyway
....DR = Nothing
....SqlConn = Nothing
....SqlComm = Nothing
'and thats it
.End Sub
```

