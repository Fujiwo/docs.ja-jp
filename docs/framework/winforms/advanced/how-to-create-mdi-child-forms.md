---
title: '方法 : MDI 子フォームを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- MDI [Windows Forms], creating forms
- child forms
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
ms.openlocfilehash: d4351e88de896f366ae2c4050f0e1c32aa0188a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527500"
---
# <a name="how-to-create-mdi-child-forms"></a>方法 : MDI 子フォームを作成する
MDI 子フォームの不可欠な要素は、[マルチ ドキュメント インターフェイス (MDI) アプリケーション](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)ユーザー操作の中心となるため、します。  
  
 次の手順では、ほとんどのワード プロセッシング アプリケーションに似ている <xref:System.Windows.Forms.RichTextBox> コントロールを表示する MDI 子フォームを作成します。 <xref:System.Windows.Forms> コントロールを、<xref:System.Windows.Forms.DataGridView> コントロールやコントロールを組み合わせたその他のコントロールで置き換えることで、さまざまな可能性のある MDI 子ウィンドウ (およびその拡張としての MDI アプリケーション) を作成できます。  
  
> [!NOTE]
>  実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。 詳細については、「[Visual Studio での開発設定のカスタマイズ](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)」を参照してください。  
  
### <a name="to-create-mdi-child-forms"></a>MDI 子フォームを作成するには  
  
1.  新しい Windows フォーム プロジェクトを作成します。 **プロパティ ウィンドウ**、フォームの次のように設定します。 その<xref:System.Windows.Forms.Form.IsMdiContainer%2A>プロパティを`true`、およびその`WindowsState`プロパティを`Maximized`です。  
  
     これによって、フォームが子ウィンドウの MDI コンテナーとして指定されます。  
  
2.  `Toolbox` から、<xref:System.Windows.Forms.MenuStrip> コントロールをフォームにドラッグします。 設定の`Text`プロパティを**ファイル**です。  
  
3.  横にある省略記号 (...) をクリックして、**項目**プロパティ、およびクリック**追加**を 2 つの子ツール ストリップのメニュー項目を追加します。 設定、`Text`プロパティにこれらの項目を**新規**と**ウィンドウ**します。  
  
4.  **ソリューション エクスプ ローラー**プロジェクトを右クリックしをポイントし、**追加**、し、**新しい項目の追加**です。  
  
5.  **新しい項目の追加**ダイアログ ボックスで、 **Windows フォーム**(Visual basic または Visual C# の場合) または**Windows フォーム アプリケーション (.NET)** (で[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)])、から**テンプレート**ウィンドウです。 **名前**ボックスに、フォームを名前**Form2**です。 クリックして、**開く**フォームをプロジェクトに追加するボタンです。  
  
    > [!NOTE]
    >  この手順で作成した、MDI 子フォームは、標準の Windows フォームです。 そのため、フォームの透明度を制御できる <xref:System.Windows.Forms.Form.Opacity%2A> プロパティを持っています。 ただし、<xref:System.Windows.Forms.Form.Opacity%2A> プロパティは最上位レベルのウィンドウ用に設計されています。 描画に関する問題が発生する可能性があるため、MDI 子フォームと共に使用しないでください。  
  
     このフォームは、MDI 子フォーム用のテンプレートになります。  
  
     **Windows フォーム デザイナー**が開き、表示する**Form2**です。  
  
6.  **ツールボックス**、ドラッグ、 **RichTextBox**をフォームにコントロールできます。  
  
7.  **プロパティ**ウィンドウで、設定、`Anchor`プロパティを**Top、Left**と`Dock`プロパティを**塗りつぶし**です。  
  
     これにより、フォームがサイズ変更された場合でも、<xref:System.Windows.Forms.RichTextBox> コントロールが MDI 子フォームの領域を完全に塗りつぶします。  
  
8.  ダブルクリックして、**新規**メニュー項目を作成する、<xref:System.Windows.Forms.Control.Click>イベント ハンドラー。  
  
9. ユーザーがクリックしたときに、新しい MDI 子フォームを作成するには、次のようなコードを挿入、**新規**メニュー項目。  
  
    > [!NOTE]
    >  次の例では、イベント ハンドラーが `MenuItem2` の <xref:System.Windows.Forms.Control.Click> イベントを処理します。 注意して、アプリケーション アーキテクチャの仕様によっては、**新規**メニュー項目ができない可能性があります`MenuItem2`です。  
  
    ```vb  
    Protected Sub MDIChildNew_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MenuItem2.Click  
       Dim NewMDIChild As New Form2()  
       'Set the Parent Form of the Child window.  
       NewMDIChild.MdiParent = Me  
       'Display the new form.  
       NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    protected void MDIChildNew_Click(object sender, System.EventArgs e){  
       Form2 newMDIChild = new Form2();  
       // Set the Parent Form of the Child window.  
       newMDIChild.MdiParent = this;  
       // Display the new form.  
       newMDIChild.Show();  
    }  
    ```  
  
    ```cpp  
    private:  
       void menuItem2_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          Form2^ newMDIChild = gcnew Form2();  
          // Set the Parent Form of the Child window.  
          newMDIChild->MdiParent = this;  
          // Display the new form.  
          newMDIChild->Show();  
       }  
    ```  
  
     [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)] で、次の `#include` ディレクティブを Form1.h の先頭に追加します。  
  
    ```cpp  
    #include "Form2.h"  
    ```  
  
10. 上部にあるドロップダウン リストで、**プロパティ**ウィンドウに対応するメニュー ストリップを選択して、**ファイル** メニュー ストリップと、<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>プロパティを Window<xref:System.Windows.Forms.ToolStripMenuItem>です。  
  
     これにより、**ウィンドウ** メニューのアクティブな子ウィンドウの横にチェック マークが付いた開いている MDI 子ウィンドウのリストを保持します。  
  
11. F5 キーを押してアプリケーションを実行します。 選択して**新規**から、**ファイル**] メニューの [新しい MDI 子フォームでの保持を作成することができます、**ウィンドウ**メニュー項目。  
  
    > [!NOTE]
    >  MDI 子フォームが (通常はメニュー項目のメニュー構造を持つ) <xref:System.Windows.Forms.MainMenu> コンポーネントを持っていて、(通常はメニュー項目のメニュー構造を持つ) <xref:System.Windows.Forms.MainMenu> コンポーネントを持つ MDI 親フォーム内で開いている場合、<xref:System.Windows.Forms.MenuItem.MergeType%2A> プロパティ (およびオプションで <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> プロパティ) を設定した場合に、メニュー項目が自動的にマージされます。 両方の <xref:System.Windows.Forms.MainMenu> コンポーネント、および子フォームのすべてのメニュー項目の <xref:System.Windows.Forms.MenuItem.MergeType%2A> プロパティを <xref:System.Windows.Forms.MenuMerge.MergeItems> に設定します。 また、<xref:System.Windows.Forms.MenuItem.MergeOrder%2A> プロパティを設定し、両方のメニューのメニュー項目が指定した順序で表示されるようにします。 さらに、MDI 親フォームを閉じた時に、MDI 親の <xref:System.Windows.Forms.Form.Closing> イベントが発生する前に、各 MDI 子フォームが <xref:System.Windows.Forms.Form.Closing> イベントを発生させます。 MDI 子の <xref:System.Windows.Forms.Form.Closing> イベントをキャンセルしても、MDI 親の <xref:System.Windows.Forms.Form.Closing> イベントの発生を防ぐことはできません。ただし、MDI 親の <xref:System.Windows.Forms.Form.Closing> イベントの <xref:System.ComponentModel.CancelEventArgs> 引数は `true` に設定されます。 <xref:System.ComponentModel.CancelEventArgs> 引数を `false` に設定することで、MDI 親レポートとすべての MDI 子フォームを強制的に閉じることができます。  
  
## <a name="see-also"></a>関連項目  
 [マルチ ドキュメント インターフェイス (MDI) アプリケーション](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [方法: MDI 親フォームを作成する](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [方法: アクティブな MDI 子フォームを特定する](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 [方法: アクティブな MDI 子フォームにデータを送信する](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 [方法: MDI 子フォームを配置する](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)
