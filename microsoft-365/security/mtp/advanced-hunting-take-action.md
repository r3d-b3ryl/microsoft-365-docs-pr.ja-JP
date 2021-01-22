---
title: Microsoft 365 Defender で高度な検索クエリ結果に対してアクションを実行する
description: 高度な検索クエリ結果で脅威と影響を受ける資産に迅速に対処する
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、アクションの実行
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9e8ad544cfe17d0d8e5c895e208b42ec56555565
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932180"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>高度な検索クエリ結果に対してアクションを実行する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

強力で包括的なアクション オプションを使用して、高度な検索[](advanced-hunting-overview.md)で見つけた脅威を迅速に含め、侵害された資産に対処できます。 これらのオプションを使用すると、次の手順を実行できます。

- デバイスでさまざまなアクションを実行する
- ファイルを検疫する

## <a name="required-permissions"></a>必要なアクセス許可
高度な検索を通じてアクションを実行するには、デバイスで修復アクションを送信するためのアクセス許可を持つ Microsoft Defender for Endpoint の役割 [が必要です](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)。 アクションを実行できない場合は、次のアクセス許可の取得についてグローバル管理者に問い合わせてください。

*脅威と脆弱性>管理に対するアクティブな修復アクション - 修復処理*

## <a name="take-various-actions-on-devices"></a>デバイスでさまざまなアクションを実行する
クエリ結果の列で識別されるデバイスに対して、次 `DeviceId` のアクションを実行できます。

- 影響を受けるデバイスを分離して感染を阻止するか、攻撃が横方向に移動するのを防ぐ
- 調査パッケージを収集して、より多くの調査情報を取得する
- ウイルス対策スキャンを実行して、最新のセキュリティ インテリジェンス更新プログラムを使用して脅威を検出および削除する
- 自動調査を開始して、デバイスや他の影響を受ける可能性があるデバイス上の脅威をチェックして修復する
- アプリの実行を Microsoft が署名した実行可能ファイルにのみ制限し、マルウェアまたは他の信頼されていない実行可能ファイルによる以降の脅威アクティビティを防止する

これらの対応アクションが Microsoft Defender for Endpoint を介して実行される方法の詳細については、デバイスでの対応 [アクションに関するページをご覧ください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)。
   
## <a name="quarantine-files"></a>ファイルを検疫する
ファイルに検疫アクション *を* 展開して、検出時に自動的に検疫することができます。 このアクションを選択する場合は、次の列から選択して、検疫するクエリ結果内のファイルを特定できます。

- `SHA1` — 高度な検索テーブルでは、記録されたアクションの影響を受けたファイルの SHA-1 です。 たとえば、ファイルがコピーされた場合、これはコピーされたファイルです。
- `InitiatingProcessSHA1` — 最も高度な検索テーブルでは、記録されたアクションを開始するファイルです。 たとえば、子プロセスが起動された場合、これは親プロセスになります。 
- `SHA256` — これは、列で識別されるファイルに相当する SHA-256 `SHA1` です。
- `InitiatingProcessSHA256` — これは、列で識別されるファイルに相当する SHA-256 `InitiatingProcessSHA1` です。

検疫アクションの実行方法とファイルの復元方法の詳細については、ファイルに対する対応 [アクションに関するページを参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)。

>[!NOTE]
>ファイルを見つけて検疫するには、クエリ結果にデバイス識別子 `DeviceId` として値を含める必要があります。  

## <a name="take-action"></a>アクションを実行する
説明されているアクションのいずれかを実行するには、クエリ結果で 1 つ以上のレコードを選択し、[アクションの実行] を **選択します**。 ウィザードでは、希望するアクションを選択して送信するプロセスについて説明します。

![レコードを検査するパネルを含む選択されたレコードの画像](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>実行されたアクションを確認する
各アクションは、アクション センターの履歴[](mtp-action-center.md)( security.microsoft.com/action-center/history ) の下のアクション センター  >  [に個別に記録されます](https://security.microsoft.com/action-center/history)。 アクション センターに移動して、各アクションの状態を確認します。
 
## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [アクション センターの概要](mtp-action-center.md)
