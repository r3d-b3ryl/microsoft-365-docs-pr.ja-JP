---
title: Microsoft の脅威保護で高度な検索クエリ結果に対してアクションを実行する
description: 高度な検索のクエリ結果の脅威と影響を受ける資産を迅速に解決する
keywords: 高度な検索、脅威の探し、サイバーの脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、take action
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 3d2df325198c420cb2444a74b6c3507657355012
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412096"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>高度な検索クエリ結果に対してアクションを実行する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

強力で包括的なアクションオプションを使用することにより、 [高度な](advanced-hunting-overview.md) 検索によって検出された脅威や、侵害された資産に対処することができます。 これらのオプションを使用すると、次のことができます。

- デバイスでさまざまなアクションを実行する
- ファイルの検疫

## <a name="required-permissions"></a>必要なアクセス許可
高度な検索を通じてアクションを実行できるようにするには、 [デバイスで修復操作を送信するためのアクセス許可](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)を持つ MICROSOFT Defender ATP の役割が必要です。 アクションを実行できない場合は、次のアクセス許可の取得について全体管理者に問い合わせてください。

*アクティブな修復アクション > 脅威と脆弱性の管理-修復処理*

## <a name="take-various-actions-on-devices"></a>デバイスでさまざまなアクションを実行する
クエリ結果の列で識別されるデバイスに対して、次の操作を行うことができ `DeviceId` ます。

- 影響を受けるデバイスを分離して感染を抑制するか、laterally の移行を防ぐ
- 調査パッケージを収集して、より法的情報を入手する
- ウイルス対策スキャンを実行して、最新のセキュリティインテリジェンス更新を使用して脅威を見つけて削除する
- デバイスとその他の影響を受けるデバイス上の脅威をチェックおよび修復するための自動化された調査を開始します。
- Microsoft 署名済みの実行可能ファイルのみにアプリの実行を制限し、マルウェアまたは他の信頼されていない実行可能ファイルからの後続の脅威を防止します。

Microsoft Defender ATP を使用してこれらの応答アクションを実行する方法の詳細については、「 [デバイスに対する応答アクションについて](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)」を参照してください。
   
## <a name="quarantine-files"></a>ファイルの検疫
*検疫*アクションをファイルに展開して、検出時に自動的に検疫されるようにすることができます。 このアクションを選択する場合、次の列から選択して、クエリ結果のどのファイルを検疫するかを指定できます。

- `SHA1` —最も高度な検索テーブルの場合、これは、記録された操作の影響を受けたファイルの SHA-1 です。 たとえば、ファイルがコピーされた場合、これはコピーされたファイルになります。
- `InitiatingProcessSHA1` —最も高度な検索テーブルの場合、これは、記録されたアクションを開始するためのファイルです。 たとえば、子プロセスが起動された場合、これは親プロセスになります。 
- `SHA256` —これは、列で指定されたファイルに対応する SHA-1 256 に相当し `SHA1` ます。
- `InitiatingProcessSHA256` —これは、列で指定されたファイルに対応する SHA-1 256 に相当し `InitiatingProcessSHA1` ます。

検疫アクションの実行方法とファイルの復元方法の詳細については、「 [ファイルに対する応答アクションについ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)て」を参照してください。

>[!NOTE]
>ファイルを検索し、それらを検疫するために、クエリ結果には `DeviceId` デバイス識別子として値も含める必要があります。  

## <a name="take-action"></a>アクションを実行する
上記の操作のいずれかを実行するには、クエリ結果で1つ以上のレコードを選択し、[ **アクションを実行**] を選択します。 ウィザードに従って、優先する操作を選択して送信するプロセスを実行できます。

![レコードを検査するためのパネルがある、選択されたレコードのイメージ](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>実行されたアクションを確認する
各アクションは、アクション**センター**の[action center](mtp-action-center.md)  >  **履歴**([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)) の下にあるアクションセンターに個別に記録されます。 アクションセンターに移動して、各アクションの状態を確認します。
 
## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [アクションセンターの概要](mtp-action-center.md)
