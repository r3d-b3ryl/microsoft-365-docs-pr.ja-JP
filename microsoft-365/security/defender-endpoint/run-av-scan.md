---
title: ウイルス対策スキャン API を実行する
description: この API を使用して、デバイスでのウイルス対策スキャンの実行に関連する呼び出しを作成します。
keywords: apis、graph API、サポートされている API、分離からデバイスを削除する
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
ms.openlocfilehash: 3208ff32c2adda051b79fea684af915a909dd062
ms.sourcegitcommit: 954c8af658adb270fe843991e048c6a30e86e77c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2022
ms.locfileid: "62428819"
---
# <a name="run-antivirus-scan-api"></a>ウイルス対策スキャン API を実行する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:** 
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

デバイスでMicrosoft Defender ウイルス対策スキャンを開始します。

## <a name="limitations"></a>制限事項

1. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

[!include[Device actions note](../../includes/machineactionsnote.md)]

> [!IMPORTANT]
>
> - このアクションは、Windows 10、バージョン 1709 以降、およびWindows 11のデバイスで使用できます。
> - Microsoft Defender ウイルス対策 (Microsoft Defender AV) スキャンは、Microsoft Defender ウイルス対策がアクティブなウイルス対策ソリューションであるかどうかに関係なく、他のウイルス対策ソリューションと共に実行できます。 Microsoft Defender ウイルス対策はパッシブ モードにすることができます。 詳細については、「[Microsoft Defender ウイルス対策の互換性](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-compatibility)」を参照してください。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API の使用」を](apis-intro.md)参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Machine.Scan|'スキャン マシン'
委任 (職場または学校のアカウント)|Machine.Scan|'スキャン マシン'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーには、少なくとも次のロールアクセス許可が必要です:"アクティブ修復アクション" (詳細については、 [ロールの作成と管理](user-roles.md) に関するページを参照してください)
> - ユーザーは、デバイス グループの設定に基づいてデバイスにアクセスできる必要があります (詳細については、「 [デバイス グループの作成と管理](machine-groups.md) 」を参照してください)

## <a name="http-request"></a>HTTP 要求

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/runAntiVirusScan
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**。
Content-Type|string|application/json

## <a name="request-body"></a>要求本文

要求本文で、次のパラメーターを含む JSON オブジェクトを指定します。

パラメーター|種類|説明
:---|:---|:---
コメント|文字列|アクションに関連付けるコメント。 **必須**。
ScanType|String|スキャンの種類を定義します。 **必須**。

**ScanType** は実行するスキャンの種類を制御し、次のいずれかを指定できます。

- **クイック**: デバイスでクイック スキャンを実行する
- **Full**: デバイスでフル スキャンを実行する

## <a name="response"></a>応答

成功した場合、このメソッドは応答本文で 201、Created 応答コード、 _MachineAction_ オブジェクトを返します。

同じデバイスのウイルス対策スキャンを実行するために複数の API 呼び出しを送信すると、"保留中のマシン アクション" または HTTP 400 が返され、"Action is already progress" というメッセージが表示されます。

## <a name="example"></a>例

### <a name="request"></a>要求

以下は、要求の例です。

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runAntiVirusScan 
```

```json
{
  "Comment": "Check machine for viruses due to alert 3212",
  "ScanType": "Full"
}
```
