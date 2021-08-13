---
title: ウイルス対策スキャン API の実行
description: この API を使用して、デバイスでのウイルス対策スキャンの実行に関連する呼び出しを作成します。
keywords: apis、graph api、サポートされている api、分離からデバイスを削除する
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: a8c21b49e4de23b2f8a822eb06a3d172202d3cf4b8b1c38bec6f23bf08e381b7
ms.sourcegitcommit: 4f074a8598a430344a2361728a64b8b8c0e1d215
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2021
ms.locfileid: "54523323"
---
# <a name="run-antivirus-scan-api"></a>ウイルス対策スキャン API の実行

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

デバイスMicrosoft Defender ウイルス対策スキャンを開始します。

## <a name="limitations"></a>制限事項

1. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

[!include[Device actions note](../../includes/machineactionsnote.md)]

> [!IMPORTANT]
>
> - このアクションは、バージョン 1709 以降Windows 10デバイスで使用できます。
> - Microsoft Defender AV Microsoft Defender ウイルス対策(Microsoft Defender AV) スキャンは、アクティブなウイルス対策ソリューションかどうかに関して、他のウイルス対策ソリューションと一緒に実行できます。 Microsoft Defender AV はパッシブ モードにできます。 詳細については、「互換性」[をMicrosoft Defender ウイルス対策してください](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility.md)。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Machine.Scan|'スキャン マシン'
委任 (職場または学校のアカウント)|Machine.Scan|'スキャン マシン'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'Active 修復アクション' (詳細については、「役割の作成と管理 [」](user-roles.md) を参照してください)
> - ユーザーは、デバイス グループ設定に基づいてデバイスにアクセスする必要があります (詳細については、「 [デバイス](machine-groups.md) グループの作成と管理」を参照してください)

## <a name="http-request"></a>HTTP 要求

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/runAntiVirusScan
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**
Content-Type|string|application/json

## <a name="request-body"></a>要求本文

要求本文で、JSON オブジェクトに次のパラメーターを指定します。

パラメーター|種類|説明
:---|:---|:---
コメント|文字列|アクションに関連付けるコメント。 **必須**
ScanType|String|スキャンの種類を定義します。 **必須**

**ScanType** は、実行するスキャンの種類を制御し、次のいずれかを指定できます。

- **クイック**: デバイスでクイック スキャンを実行する
- **[完全**] : デバイスでフル スキャンを実行する

## <a name="response"></a>応答

成功した場合、このメソッドは応答本文に 201、Created 応答コード _、MachineAction_ オブジェクトを返します。

## <a name="example"></a>例

### <a name="request"></a>要求

以下は、要求の例です。

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runAntiVirusScan 
```

```json
{
  "Comment": "Check machine for viruses due to alert 3212",
  "ScanType&quot;: &quot;Full"
}
```
