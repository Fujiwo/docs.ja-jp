---
title: エンドポイント
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: 5d597e9e029cec3552c94b47a64dfbf36d933e67
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487647"
---
# <a name="endpoint"></a>エンドポイント
エンドポイント  
  
## <a name="syntax"></a>構文  
  
```  
class Endpoint  
{  
  string Address;  
  string AddressHeaders[];  
  string AddressIdentity;  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  Binding Binding;  
  string ContractName;  
  string CounterInstanceName;  
  string ListenUri;  
  string Name;  
  sint32 ProcessId;  
  Contract ref;  
};  
```  
  
## <a name="methods"></a>メソッド  
 Endpoint クラスは次のメソッドを定義します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[GetOperationCounterInstanceName](../../../../../docs/framework/wcf/diagnostics/wmi/getoperationcounterinstancename.md)|操作パフォーマンス カウンターのインスタンスの名前を取得します。|  
  
## <a name="properties"></a>プロパティ  
 Endpoint クラスには次のプロパティがあります。  
  
### <a name="address"></a>Address  
 データ型: string  
  
 アクセスの種類 : 読み取り専用  
  
 エンドポイントのアドレスを格納している URI。  
  
### <a name="addressheaders"></a>AddressHeaders  
 データ型 : string array  
  
 アクセスの種類 : 読み取り専用  
  
 このエンドポイントに接続しているアドレス ヘッダーのコレクション  
  
### <a name="addressidentity"></a>AddressIdentity  
 データ型: string  
  
 アクセスの種類 : 読み取り専用  
  
 エンドポイントの ID  
  
### <a name="appdomainid"></a>AppDomainId  
 データ型 : sint32  
  
 アクセスの種類 : 読み取り専用  
  
 エンドポイントをホストする appdomain の appdomain ID  
  
### <a name="behaviors"></a>ビヘイビアー  
 データ型 : Behavior array  
  
 アクセスの種類 : 読み取り専用  
  
 このエンドポイントが実装する動作のコレクション  
  
### <a name="binding"></a>バインディング  
 データ型 : Binding  
  
 アクセスの種類 : 読み取り専用  
  
 このエンドポイントが使用するバインディング  
  
### <a name="contractname"></a>ContractName  
 データ型: string  
  
 アクセスの種類 : 読み取り専用  
  
 このエンドポイントが公開するコントラクトを指定する文字列  
  
### <a name="counterinstancename"></a>CounterInstanceName  
 データ型: string  
  
 アクセスの種類 : 読み取り専用  
  
 エンドポイントのパフォーマンス カウンターのインスタンス名  
  
### <a name="listenuri"></a>ListenUri  
 データ型: string  
  
 アクセスの種類 : 読み取り専用  
  
 エンドポイントがリッスンする URI  
  
### <a name="name"></a>名前  
 データ型: string  
  
 アクセスの種類 : 読み取り専用  
  
 このエンドポイントの一意の名前  
  
### <a name="processid"></a>ProcessId  
 データ型 : sint32  
  
 アクセスの種類 : 読み取り専用  
  
 エンドポイントをホストするプロセスのプロセス ID  
  
### <a name="ref"></a>ref  
 データ型 : Contract  
  
 アクセスの種類 : 読み取り専用  
  
 このエンドポイントが公開しているコントラクト。  
  
## <a name="requirements"></a>要件  
  
|MOF|Servicemodel.mof にて宣言済み。|  
|---------|-----------------------------------|  
|Namespace|root\ServiceModel で定義|
