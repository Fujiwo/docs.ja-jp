---
title: '方法 : ファイルからテキストを読み取る'
ms.date: 06/19/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, reading text from files
- reading text files
- reading data, text files
- data streams, reading text from files
- I/O [.NET Framework], reading text from files
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b7c54e5e55770f3df44819cdf6d2d2c866f7e0fc
ms.sourcegitcommit: 640cee8fc5d256cdd80e5b80240469feac10499e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2018
ms.locfileid: "36298163"
---
# <a name="how-to-read-text-from-a-file"></a>方法 : ファイルからテキストを読み取る
次に、.NET デスクトップ アプリを使用してテキスト ファイルから同期でテキストを読み取る方法と非同期でテキストを読み取る方法の例を示します。 どちらの例でも、<xref:System.IO.StreamReader> クラスのインスタンスを作成する場合に、ファイルの相対パスまたは絶対パスを指定します。 次の例では、TestFile.txt という名前のファイルがアプリケーションと同じフォルダーにあることを前提とします。  
  
 Windows ランタイムではファイルに対する読み取りと書き込みに別のストリーム型が用意されているため、これらのコード例は Windows ストア アプリの開発には適用されません。 Windows ストア アプリのファイルからテキストを読み取る方法を示す例については、「[Quickstart: Reading and writing files](https://docs.microsoft.com/en-us/previous-versions/windows/apps/hh758325(v=win.10))」 (クイック スタート: ファイルの読み取りと書き込み) を参照してください。 .NET Framework ストリームと Windows ランタイム ストリームを変換する方法を示す例は、「[方法: .NET Framework ストリームと Windows ランタイム ストリームの間で変換を行う](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、コンソール アプリケーション内での同期読み取り操作を示します。 この例では、ストリーム リーダーを使用してテキスト ファイルを開き、内容を文字列にコピーして、文字列をコンソールに出力します。  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example"></a>例  
 次の例では、Windows Presentation Foundation (WPF) アプリケーション内での非同期読み取り操作を示します。  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source6.cs#6)]
 [!code-vb[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source6.vb#6)]  
  
## <a name="see-also"></a>参照  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 [非同期ファイル I/O](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [NIB: 方法: ディレクトリ一覧を作成する](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)  
 [クイック スタート: ファイルの読み取りと書き込み](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx)  
 [方法: .NET Framework ストリームと Windows ランタイム ストリームの間で変換を行う](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
 [方法: 新しく作成されたデータ ファイルに対して読み書きする](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [方法: ログ ファイルを開いて情報を追加する](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [方法: ファイルにテキストを書き込む](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [方法: 文字列から文字を読み取る](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [方法: 文字列に文字を書き込む](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [ファイルおよびストリーム入出力](../../../docs/standard/io/index.md)
