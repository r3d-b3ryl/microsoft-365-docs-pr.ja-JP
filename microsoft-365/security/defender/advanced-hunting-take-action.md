---
title: Microsoft 365 Defenderで高度なハンティング クエリの結果に対してアクションを実行する
description: 高度なハンティング クエリの結果で脅威と影響を受ける資産に迅速に対処する
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, アクションを実行する
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: c83370c302b10159d4d2325e66224685ab232cad
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479512"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>高度なハンティング クエリの結果に対してアクションを実行する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

強力で包括的なアクション オプションを使用して、 [高度な捜索](advanced-hunting-overview.md) で見つけた脅威をすばやく含めたり、侵害された資産に対処したりできます。 これらのオプションを使用すると、次のことができます。

- デバイスでさまざまなアクションを実行する
- 検疫ファイル

## <a name="required-permissions"></a>必要なアクセス許可
高度な捜索を通じてデバイスに対してアクションを実行するには、[デバイスに修復アクションを送信するためのアクセス許可](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)を持つMicrosoft Defender for Endpointのロールが必要です。 アクションを実行できない場合は、次のアクセス許可の取得についてグローバル管理者に問い合わせてください。

*脅威と脆弱性の管理>アクティブな修復アクション - 修復処理*

高度な捜索を通じて電子メールに対してアクションを実行するには、[メールを検索および消去](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)するためのMicrosoft Defender for Office 365のロールが必要です。

## <a name="take-various-actions-on-devices"></a>デバイスでさまざまなアクションを実行する
クエリ結果の列で識別されたデバイスでは、次の `DeviceId` アクションを実行できます。

- 影響を受けるデバイスを隔離して感染を封じ込めるか、攻撃が横方向に移動するのを防ぐ
- 調査パッケージを収集して、より多くのフォレンジック情報を取得する
- ウイルス対策スキャンを実行して、最新のセキュリティ インテリジェンス更新プログラムを使用して脅威を見つけて削除する
- 自動調査を開始して、デバイスや影響を受けるその他のデバイス上の脅威を確認して修復する
- アプリの実行を Microsoft 署名された実行可能ファイルのみに制限し、マルウェアやその他の信頼されていない実行可能ファイルによる後続の脅威アクティビティを防止する

これらの応答アクションがMicrosoft Defender for Endpointを介して実行される方法の詳細については、[デバイスでの応答アクションに関する記事を参照してください](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)。
   
### <a name="quarantine-files"></a>検疫ファイル
*ファイルに検疫* アクションを展開して、検出されたときに自動的に検疫されるようにすることができます。 このアクションを選択するときは、次の列から選択して、検疫するクエリ結果のファイルを特定できます。

- `SHA1`: ほとんどの高度なハンティング テーブルでは、この列は、記録されたアクションの影響を受けたファイルの SHA-1 を参照します。 たとえば、ファイルがコピーされた場合、この影響を受けるファイルはコピーされたファイルになります。
- `InitiatingProcessSHA1`: ほとんどの高度なハンティング テーブルでは、この列は記録されたアクションの開始を担当するファイルを参照します。 たとえば、子プロセスが起動された場合、このイニシエーター ファイルは親プロセスの一部になります。 
- `SHA256`: この列は、列によって `SHA1` 識別されるファイルに相当する SHA-256 です。
- `InitiatingProcessSHA256`: この列は、列によって `InitiatingProcessSHA1` 識別されるファイルに相当する SHA-256 です。

検疫アクションの実行方法とファイルの復元方法の詳細については、 [ファイルに対する応答アクションに関するページを参照](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)してください。

>[!NOTE]
>ファイルを見つけて検疫するには、クエリ結果にデバイス識別子として値も含める `DeviceId` 必要があります。  

説明されているアクションのいずれかを実行するには、クエリ結果で 1 つ以上のレコードを選択し、[ **アクションの実行**] を選択します。 ウィザードでは、優先するアクションを選択して送信するプロセスについて説明します。

:::image type="content" source="../../media/take-action-multiple.png" alt-text="Microsoft 365 Defender ポータルでアクションを実行するオプション" lightbox="../../media/take-action-multiple.png":::


## <a name="take-various-actions-on-emails"></a>メールに対してさまざまなアクションを実行する
デバイスに重点を置いた修復手順とは別に、クエリ結果から電子メールに対していくつかのアクションを実行することもできます。 アクションを実行するレコードを選択し、[アクションの **実行**] を選択し、[ **アクションの選択]** で次の中から選択します。
- `Move to mailbox folder` - 電子メール メッセージを [迷惑メール]、[受信トレイ]、または [削除済みアイテム] フォルダーに移動するには、これを選択します

   :::image type="content" source="../../media/advanced-hunting-take-actions-email.png" alt-text="Microsoft 365 Defender ポータルでアクションを実行するオプション" lightbox="../../media/advanced-hunting-take-actions-email.png":::

- `Delete email` - これを選択して、電子メール メッセージを [削除済みアイテム] フォルダーに移動するか (**論理的に削除**) するか、完全に削除します (**ハード削除**)

   :::image type="content" source="../../media/advanced-hunting-take-actions-email-del.png" alt-text="Microsoft 365 Defender ポータルの [アクションの実行] オプション" lightbox="../../media/advanced-hunting-take-actions-email-del.png":::

修復名と、アクション センターの履歴で簡単に追跡するために実行されるアクションの簡単な説明を指定することもできます。 承認 ID を使用して、アクション センターでこれらのアクションをフィルター処理することもできます。 この ID は、ウィザードの最後に提供されます。

:::image type="content" source="../../media/choose-email-actions-entities.png" alt-text="エンティティの選択アクションを示すアクションの実行ウィザード" lightbox="../../media/choose-email-actions-entities.png":::

これらの電子メール アクションは、 [カスタム検出](custom-detections-overview.md) にも適用されます。


## <a name="review-actions-taken"></a>実行されたアクションを確認する
各アクションは、[[アクション センター](m365d-action-center.md)履歴 **] (**[security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)) のアクション **センター** > に個別に記録されます。 アクション センターに移動して、各アクションの状態を確認します。
 
>[!NOTE]
>この記事の一部のテーブルは、Microsoft Defender for Endpointでは使用できない場合があります。 [Microsoft 365 Defenderを有効にして](m365d-enable.md)、より多くのデータ ソースを使用して脅威を検出します。 高度なハンティング クエリをMicrosoft Defender for Endpointから移行するの手順に従って、[高度なハンティング ワークフローをMicrosoft Defender for EndpointからMicrosoft 365 Defender](advanced-hunting-migrate-from-mde.md)に移動できます。

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [アクション センターの概要](m365d-action-center.md)
