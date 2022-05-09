---
title: ファイル API の停止と検疫
description: デバイスでのファイルの実行を停止し、Microsoft Defender for Endpointでファイルを削除する方法について説明します。 「例」を参照してください。
keywords: apis、graph api、サポートされている API、停止ファイルと検疫ファイル
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
ms.openlocfilehash: 1f61e238030c5c8c31e514ef76cf90ffc4b5bd92
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61300948"
---
# <a name="stop-and-quarantine-file-api"></a>ファイル API の停止と検疫

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

デバイスでのファイルの実行を停止し、削除します。

## <a name="limitations"></a>制限事項

1. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

[!include[Device actions note](../../includes/machineactionsnote.md)]

> [!IMPORTANT]
> この操作は、次の場合にのみ実行できます。
>
> - アクションを実行しているデバイスが、Windows 10、バージョン 1703 以降、またはWindows 11実行されている
> - ファイルが信頼されたサード パーティの発行元に属していないか、Microsoft によって署名されていない
> - Microsoft Defender ウイルス対策は、少なくともパッシブ モードで実行されている必要があります。 詳細については、「[Microsoft Defender ウイルス対策の互換性](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)」を参照してください。


## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API の使用」を](apis-intro.md)参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Machine.StopAndQuarantine|'停止と検疫'
アプリケーション|Machine.Read.All|'すべてのマシン プロファイルを読み取る'
アプリケーション|Machine.ReadWrite.All|'すべてのマシン情報の読み取りと書き込み'
委任 (職場または学校のアカウント)|Machine.StopAndQuarantine|'停止と検疫'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーには、少なくとも次のロールアクセス許可が必要です:"アクティブ修復アクション" (詳細については、 [ロールの作成と管理](user-roles.md) に関するページを参照してください)
> - ユーザーは、デバイス グループの設定に基づいてデバイスにアクセスできる必要があります (詳細については、「 [デバイス グループの作成と管理](machine-groups.md) 」を参照してください)

## <a name="http-request"></a>HTTP 要求

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/StopAndQuarantineFile
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
Sha1|String|デバイスで停止して検疫するファイルの Sha1。 **必須**。

## <a name="response"></a>応答

成功した場合、このメソッドは 201 - 作成された応答コードと応答本文の [Machine Action](machineaction.md) を返します。

## <a name="example"></a>例

### <a name="request"></a>要求

以下は、要求の例です。

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/StopAndQuarantineFile 
```

```json
{
  "Comment": "Stop and quarantine file on machine due to alert 441688558380765161_2136280442",
  "Sha1": "87662bc3d60e4200ceaf7aae249d1c343f4b83c9"
}
```
