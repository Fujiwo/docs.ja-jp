---
title: データ ソースのデータの更新
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 55c545e5-dcd5-4323-a5b9-3825c2157462
ms.openlocfilehash: 11c3faa85d6d0b77c4e606815aa8252188b6f67d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="updating-data-in-a-data-source"></a>データ ソースのデータの更新
データを変更する SQL ステートメント (INSERT、UPDATE、DELETE など) は行を返しません。 同様に、多くのストアド プロシージャは、アクションを実行しても行を返しません。 行を返さないコマンドを実行するには、作成、**コマンド**適切な SQL コマンドを使用してオブジェクトと**接続**など必要な**パラメーター**です。 コマンドを実行、 **ExecuteNonQuery**のメソッド、**コマンド**オブジェクト。  
  
 **ExecuteNonQuery**ステートメントまたはが実行されたストアド プロシージャによって影響を受ける行の数を表す整数を返します。 複数のステートメントが実行された場合は、実行された各ステートメントの影響を受けたレコードの合計を示す値が返されます。  
  
## <a name="example"></a>例  
 次のコード例を使用してデータベースにレコードを挿入する INSERT ステートメントを実行する**ExecuteNonQuery**です。  
  
```vb  
' Assumes connection is a valid SqlConnection.  
connection.Open()  
  
Dim queryString As String = "INSERT INTO Customers " & _  
  "(CustomerID, CompanyName) Values('NWIND', 'Northwind Traders')"  
  
Dim command As SqlCommand = New SqlCommand(queryString, connection)  
Dim recordsAffected As Int32 = command.ExecuteNonQuery()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
connection.Open();  
  
string queryString = "INSERT INTO Customers " +  
  "(CustomerID, CompanyName) Values('NWIND', 'Northwind Traders')";  
  
SqlCommand command = new SqlCommand(queryString, connection);  
Int32 recordsAffected = command.ExecuteNonQuery();  
```  
  
 次のコード例のサンプル コードで作成したストアド プロシージャを実行する[カタログ操作の実行](../../../../docs/framework/data/adonet/performing-catalog-operations.md)です。 ストアド プロシージャによって行が返されないため、 **ExecuteNonQuery**メソッドを使用するは、ストアド プロシージャは、入力パラメーターを受信し、出力パラメーターと戻り値を返します。  
  
 <xref:System.Data.OleDb.OleDbCommand>オブジェクト、 **ReturnValue**にパラメーターを追加する必要があります、**パラメーター**コレクション最初。  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim command As SqlCommand = _  
   New SqlCommand("InsertCategory" , connection)  
command.CommandType = CommandType.StoredProcedure  
  
Dim parameter As SqlParameter = _  
 command.Parameters.Add("@RowCount", SqlDbType.Int)  
parameter.Direction = ParameterDirection.ReturnValue  
  
parameter = command.Parameters.Add( _  
  "@CategoryName", SqlDbType.NChar, 15)  
  
parameter = command.Parameters.Add("@Identity", SqlDbType.Int)  
parameter.Direction = ParameterDirection.Output  
  
command.Parameters("@CategoryName").Value = "New Category"  
command.ExecuteNonQuery()  
  
Dim categoryID As Int32 = CInt(command.Parameters("@Identity").Value)  
Dim rowCount As Int32 = CInt(command.Parameters("@RowCount").Value)   
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlCommand command = new SqlCommand("InsertCategory" , connection);  
command.CommandType = CommandType.StoredProcedure;  
  
SqlParameter parameter = command.Parameters.Add(  
  "@RowCount", SqlDbType.Int);  
parameter.Direction = ParameterDirection.ReturnValue;  
  
parameter = command.Parameters.Add(  
  "@CategoryName", SqlDbType.NChar, 15);  
  
parameter = command.Parameters.Add("@Identity", SqlDbType.Int);  
parameter.Direction = ParameterDirection.Output;  
  
command.Parameters["@CategoryName"].Value = "New Category";  
command.ExecuteNonQuery();  
  
Int32 categoryID = (Int32) command.Parameters["@Identity"].Value;  
Int32 rowCount = (Int32) command.Parameters["@RowCount"].Value;  
```  
  
## <a name="see-also"></a>関連項目  
 [コマンドを使用したデータ変更](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)  
 [DataAdapter によるデータ ソースの更新](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 [コマンドおよびパラメーター](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [ADO.NET のマネージ プロバイダーと DataSet デベロッパー センター](http://go.microsoft.com/fwlink/?LinkId=217917)
