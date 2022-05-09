---
title: マシン API を分離する
description: 分離マシン API を使用して、Microsoft Defender for Endpointの外部ネットワークへのアクセスからデバイスを分離する方法について説明します。
keywords: apis、graph api、サポートされている API、デバイスの分離
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 52063135280d9e91ca531546b4ae03cf5b42ccbf
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61300792"
---
# <a name="isolate-machine-api"></a>マシン API を分離する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

外部ネットワークへのアクセスからデバイスを分離します。

## <a name="limitations"></a>制限事項

1. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

[!include[Device actions note](../../includes/machineactionsnote.md)]

> [!IMPORTANT]
>
> - 完全な分離は、Windows 10バージョン 1703 および Windows 11 上のデバイスで使用できます。
> - 選択的分離は、Windows 10、バージョン 1709 以降、およびWindows 11のデバイスで使用できます。
> - デバイスを分離する場合は、特定のプロセスと宛先のみが許可されます。 そのため、完全な VPN トンネルの背後にあるデバイスは、デバイスが分離された後、Microsoft Defender for Endpoint クラウド サービスに到達できません。 クラウド ベースの保護関連トラフィックをMicrosoft Defender for EndpointおよびMicrosoft Defender ウイルス対策するために、分割トンネリング VPN を使用することをお勧めします。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API の使用」を](apis-intro.md)参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Machine.Isolate|'マシンの分離'
委任 (職場または学校のアカウント)|Machine.Isolate|'マシンの分離'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーには、少なくとも次のロールアクセス許可が必要です:"アクティブ修復アクション" (詳細については、 [ロールの作成と管理](user-roles.md) に関するページを参照してください)
> - ユーザーは、デバイス グループの設定に基づいてデバイスにアクセスできる必要があります (詳細については、「 [デバイス グループの作成と管理](machine-groups.md) 」を参照してください)

## <a name="http-request"></a>HTTP 要求

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/isolate
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**。
Content-Type|string|application/json. **必須**。

## <a name="request-body"></a>要求本文

要求本文で、次のパラメーターを含む JSON オブジェクトを指定します。

パラメーター|種類|説明
:---|:---|:---
コメント|文字列|アクションに関連付けるコメント。 **必須**。
IsolationType|String|分離の種類。 使用できる値は、"完全" または "選択的" です。

**IsolationType** は、実行する分離の種類を制御し、次のいずれかを指定できます。

- 完全: 完全分離
- 選択的: ネットワークにアクセスするアプリケーションの限定されたセットのみを制限する (詳細については、「ネットワーク [からデバイスを分離する](respond-machine-alerts.md#isolate-devices-from-the-network) 」を参照)

## <a name="response"></a>応答

成功した場合、このメソッドは 201 - 作成された応答コードと応答本文の [Machine Action](machineaction.md) を返します。

## <a name="example"></a>例

### <a name="request"></a>要求

以下は、要求の例です。

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/isolate
```

```json
{
  "Comment": "Isolate machine due to alert 1234",
  "IsolationType": "Full" 
}
```

- デバイスを分離から解放するには、「分離 [からデバイスを解放](unisolate-machine.md)する」を参照してください。
