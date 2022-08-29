---
title: アプリ実行 API を制限する
description: この API を使用して、アプリケーションの実行を制限することに関連する呼び出しを作成します。
keywords: apis、graph api、サポートされている API、調査パッケージの収集
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
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 765f08fe38d8b04d76c191c9e31c7a33c9b56ff7
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67331585"
---
# <a name="restrict-app-execution-api"></a>アプリ実行 API を制限する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

定義済みのセットを除く、デバイス上のすべてのアプリケーションの実行を制限します。

## <a name="limitations"></a>制限事項

1. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

[!include[Device actions note](../../includes/machineactionsnote.md)]


> [!IMPORTANT]
>
> - このアクションは、Windows 10、バージョン 1709 以降、およびWindows 11のデバイスで使用できます。
> - この機能は、組織で Microsoft Defender ウイルス対策を使用している場合に使用できます。
> - このアクションは、Windows Defenderアプリケーション制御コード整合性ポリシーの形式と署名の要件を満たす必要があります。 詳細については、「 [コード整合性ポリシーの形式と署名](/windows/device-security/device-guard/requirements-and-deployment-planning-guidelines-for-device-guard#code-integrity-policy-formats-and-signing)」を参照してください。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API の使用」を](apis-intro.md)参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Machine.RestrictExecution|'コードの実行を制限する'
委任 (職場または学校のアカウント)|Machine.RestrictExecution|'コードの実行を制限する'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーには、少なくとも次のロールアクセス許可が必要です:"アクティブ修復アクション" (詳細については、 [ロールの作成と管理](user-roles.md) に関するページを参照してください)
> - ユーザーは、デバイス グループの設定に基づいてデバイスにアクセスできる必要があります (詳細については、「 [デバイス グループの作成と管理](machine-groups.md) 」を参照してください)

## <a name="http-request"></a>HTTP 要求

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/restrictCodeExecution
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

## <a name="response"></a>応答

成功した場合、このメソッドは 201 - 作成された応答コードと応答本文の [Machine Action](machineaction.md) を返します。

同じデバイスに対してアプリの実行を制限するために複数の API 呼び出しを送信すると、"保留中のマシン アクション" または HTTP 400 が返され、"Action is already progress" というメッセージが表示されます。

## <a name="example"></a>例

### <a name="request"></a>要求

以下は、要求の例です。

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/restrictCodeExecution 
```

```json
{
  "Comment": "Restrict code execution due to alert 1234"
}
```

- デバイスからコード実行制限を削除するには、「 [アプリの制限を削除する](unrestrict-code-execution.md)」を参照してください。
