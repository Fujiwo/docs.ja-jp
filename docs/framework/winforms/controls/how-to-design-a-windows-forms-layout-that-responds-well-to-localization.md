---
title: '方法 : ローカリゼーションに対応した Windows フォーム レイアウトをデザインする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
ms.openlocfilehash: aa141319e902ff96ecfb9e9a70ca66528705418d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533879"
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a>方法 : ローカリゼーションに対応した Windows フォーム レイアウトをデザインする
ローカライズが可能なフォームを作成すると、各国市場向けの開発期間が大幅に短縮されます。 <xref:System.Windows.Forms.TableLayoutPanel> コントロールを使用すると、<xref:System.Windows.Forms.Control.Text%2A> プロパティ値の変更によってコントロールのサイズが変更された際に、これに適切に応答するレイアウトを実装できます  
  
## <a name="example"></a>例  
 このフォームでは、表示される文字列値を他の言語に翻訳するときに、均等に調整されるレイアウトを作成する方法を示します。 この翻訳プロセスのことを "*ローカリゼーション*" といいます。 詳細については、「[ローカリゼーション](../../../../docs/standard/globalization-localization/localization.md)」を参照してください。  
  
 Visual Studio では、このタスクに対する広範なサポートが用意されています。  「[チュートリアル: ローカライズの際に均等に調整されるレイアウトの作成](http://msdn.microsoft.com/library/7k9fa71y\(v=vs.110\))」も参照してください。  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
1.  [方法: TableLayoutPanel コントロール内でコントロールを配置して伸縮する](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))  
  
2.  [チュートリアル: FlowLayoutPanel を使用した Windows フォーム上のコントロールの配置](http://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\))  
  
3.  [方法: TableLayoutPanel コントロールの行と列を拡大する](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))  
  
4.  [方法: TableLayoutPanel コントロールの列と行を編集する](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))  
  
5.  [チュートリアル: Windows フォーム コントロールのスマート タグを使用した共通タスクの実行](http://msdn.microsoft.com/library/xhz359sc\(v=vs.110\))  
  
6.  [チュートリアル: TableLayoutPanel を使用した Windows フォーム上のコントロールの配置](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))  
  
7.  [チュートリアル: Padding、Margin、および AutoSize プロパティを使用した Windows フォーム コントロールのレイアウト](http://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\))  
  
8.  [方法: AutoSize と TableLayoutPanel コントロールを使用して Windows フォームのローカリゼーションをサポートする](http://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\))  
  
9. [チュートリアル: データ入力用のサイズ変更可能な Windows フォームの作成](http://msdn.microsoft.com/library/991eahec\(v=vs.110\))  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
-   System、System.Data、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。  
  
 コマンドラインからこの例を Visual Basic または Visual c# のビルドについては、次を参照してください。[コマンドラインからのビルド](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)です。 この例では、Visual Studio は、新しいプロジェクトにコードを貼り付けることによってもビルドできます。  また、「 [方法: 完成した Windows フォーム コードの例を Visual Studio を使ってコンパイルして実行する](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))」も参照してください。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 [ローカリゼーション](../../../../docs/standard/globalization-localization/localization.md)
