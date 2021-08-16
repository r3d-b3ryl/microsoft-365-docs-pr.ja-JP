---
title: '[修復アクション] Microsoft 365 Defender'
description: 自動調査に続く修復アクションの概要を確認Microsoft 365 Defender
keywords: 自動化、調査、警告、トリガー、アクション、修復
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 7f34f40d5d0078c1dc0b49e2f73b5c692c6a4b315058f5d8f7c097dce6b237cb
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53902189"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>[修復アクション] Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

悪意のあるアイテムまたは不審なアイテムに対してMicrosoft 365 Defenderの自動調査中および後に、修復アクションが識別されます。 一部の種類の修復アクションは、エンドポイントとも呼ばれるデバイスで実行されます。 その他の修復アクションは、メール コンテンツに対して実行されます。 修復アクションを実行、承認、または拒否した後、自動調査が完了します。

> [!IMPORTANT]
> 修復アクションが自動的に実行されるのか、承認時にのみ実行されるのかは、オートメーション レベルなどの特定の設定によって異なります。 詳細については、次の記事を参照してください。
> - [自動調査と応答機能を構成する方法は、Microsoft 365 Defender](m365d-configure-auto-investigation-response.md)
> - [デバイスでの脅威の修復方法](../defender-endpoint/automated-investigations.md)
> - [コラボレーション コンテンツに対する電子メール&修復アクション](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

次の表は、現在サポートされている修復アクションの概要を示Microsoft 365 Defender。 

|デバイス (エンドポイント) 修復アクション  |メールの修復アクション  |
|:---------|:---------|
|- 調査パッケージの収集 <br/>- デバイスを分離する (この操作は元に戻すことができます)<br/>- オフボード マシン <br/>- リリース コードの実行 <br/>- 検疫からの解放 <br/>- 要求サンプル <br/>- コードの実行を制限する (このアクションは元に戻すことができます) <br/>- ウイルス対策スキャンを実行する <br/>- 停止と検疫      |- ブロック URL (クリック時)<br/>- 電子メール メッセージまたはクラスターを削除する<br/>- 検疫メール<br/>- メールの添付ファイルを検疫する<br/>- 外部メール転送を無効にする          |

修復アクションは、保留中の承認または既に完了したかどうかに関して、アクション センターで [表示できます](m365d-action-center.md)。

## <a name="remediation-actions-that-follow-automated-investigations"></a>自動調査に従う修復アクション

自動調査が完了すると、関連するあらゆる証拠に対して評決が下されます。 評決に応じて、修復アクションが識別されます。 修復アクションが自動的に実行される場合もあれば、修復アクションが承認を待機する場合もあります。 すべては、自動調査 [と応答の構成方法によって異なります](m365d-configure-auto-investigation-response.md)。

考えられる判定と結果を次の表に示します。

| 判定    | 影響を受けるエンティティ    | 結果|
|------|------|------|
| Malicious (悪意のある)    | デバイス (エンドポイント)    | 修復アクションは自動的に実行されます (組織の [](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups)デバイス グループが完全に設定されている場合 - 脅威 **を自動的に修復する**)|
| Malicious (悪意のある)    | メールのコンテンツ (URL または添付ファイル) | 推奨される修復アクションが承認待ちになります|
| Suspicious (不審)    | デバイスまたはメールのコンテンツ | 推奨される修復アクションが承認待ちになります|
| 脅威は検出されませんでした    | デバイスまたはメールのコンテンツ    | 必要な修復アクションはありません|


## <a name="remediation-actions-that-are-taken-manually"></a>手動で実行される修復アクション

自動調査に続く修復アクションに加えて、セキュリティ運用チームは特定の修復アクションを手動で実行できます。 これらには次のコマンドレットがあります。

- デバイスの分離やファイル検疫などのデバイスの手動操作
- 電子メール メッセージのソフト削除などの手動の電子メール アクション 
- [デバイスまたは電子](../defender-endpoint/advanced-hunting-overview.md) メールでの高度なハンティング アクション
- [迷惑](../office-365-security/threat-explorer.md) メールへのメールの移動、メールのソフト削除、メールのハード削除など、電子メール コンテンツに対するエクスプローラー アクション
- ファイル [の削除](/windows/security/threat-protection/microsoft-defender-atp/live-response) 、プロセスの停止、スケジュールされたタスクの削除などの手動のライブ応答アクション
- Microsoft Defender [for Endpoint API](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)を使用したライブ応答アクション (デバイスの分離、ウイルス対策スキャンの実行、ファイルに関する情報の取得など)

## <a name="next-steps"></a>次の手順

- [アクション センターにアクセスする](m365d-action-center.md)
- [修復アクションを表示および管理する](m365d-autoir-actions.md)
- [誤検知または誤検知に対処する](m365d-autoir-report-false-positives-negatives.md)
