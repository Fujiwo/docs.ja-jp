---
title: 正規表現におけるスレッド セーフ
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET Framework regular expressions, threads
- regular expressions, threads
- searching with regular expressions, threads
- parsing text with regular expressions, threads
- pattern-matching with regular expressions, threads
ms.assetid: 7c4a167b-5236-4cde-a2ca-58646230730f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79ca0b92cf79ca9be023925f064c1c7c16b3c9ac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33567719"
---
# <a name="thread-safety-in-regular-expressions"></a>正規表現におけるスレッド セーフ
<xref:System.Text.RegularExpressions.Regex> クラス自体はスレッド セーフであり、変更できません (読み取り専用)。 つまり、**Regex** オブジェクトは任意のスレッドで作成できます。また、スレッド間で共有できます。一致するメソッドは任意のスレッドから呼び出すことができますが、グローバルな状態を変更することはできません。  
  
 ただし、**Regex** から返された結果オブジェクト (**Match** と **MatchCollection**) は、単一のスレッドで使用する必要があります。 これらのオブジェクトの多くは、論理的に変更できませんが、実装によってパフォーマンスを改善するために一部の結果の演算を遅延させることができます。結果として、呼び出し側はオブジェクトに対するアクセスをシリアル化する必要があります。  
  
 複数のスレッドで **Regex** オブジェクトを共有する必要がある場合、同期されたメソッドを呼び出すことで、それらのオブジェクトはスレッドセーフ インスタンスに変換できます。 列挙子の例外はありますが、すべての正規表現クラスはスレッド セーフです。または、同期されたメソッドでスレッドセーフ オブジェクトに変換することができます。  
  
 列挙子は唯一の例外です。 アプリケーションはコレクション列挙子に対する呼び出しをシリアル化する必要があります。 複数のスレッドでコレクションを同時に列挙できる場合、列挙子によってスキャンされるコレクションのルート オブジェクト上の列挙子メソッドを同期する必要があります。  
  
## <a name="see-also"></a>参照  
 [.NET の正規表現](../../../docs/standard/base-types/regular-expressions.md)
