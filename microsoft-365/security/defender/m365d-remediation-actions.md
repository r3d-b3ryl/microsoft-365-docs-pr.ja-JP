---
title: Microsoft 365 Defenderの修復アクション
description: Microsoft 365 Defenderの自動調査に従う修復アクションの概要を確認する
keywords: 自動化、調査、警告、トリガー、アクション、修復
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 5605678a1fcc30719d7f838a16452ba527c554b7
ms.sourcegitcommit: a7e1d155939e862337271fbe38bf26f62bd49bdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2022
ms.locfileid: "64847051"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Microsoft 365 Defenderの修復アクション

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

Microsoft 365 Defenderの自動調査中と後に、悪意のあるアイテムまたは疑わしいアイテムに対する修復アクションが識別されます。 一部の種類の修復アクションは、エンドポイントとも呼ばれるデバイスで実行されます。 その他の修復アクションは、ID、アカウント、電子メール コンテンツに対して実行されます。 修復アクションが実行、承認、または拒否された後に、自動調査が完了します。

> [!IMPORTANT]
> 修復アクションが自動的に実行されるか、承認時にのみ実行されるかは、自動化レベルなどの特定の設定によって異なります。 詳細については、次の記事を参照してください。
>
> - [Microsoft 365 Defenderで自動調査と応答機能を構成する](m365d-configure-auto-investigation-response.md)
> - [Microsoft Defender for Identityでアクション アカウントを構成する](/defender-for-identity/manage-action-accounts)
> - [デバイスで脅威を修復する方法](../defender-endpoint/automated-investigations.md)
> - [電子メール&コラボレーション コンテンツに対する脅威と修復アクション](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

次の表は、Microsoft 365 Defenderで現在サポートされている修復アクションをまとめたものです。

|デバイス (エンドポイント) 修復アクション  |メールの修復アクション  |ユーザー (アカウント)  |
|:---------|:---------|----------|
|- 調査パッケージを収集する <br/>- デバイスを分離する (この操作は元に戻すことができます)<br/>- オフボード マシン <br/>- リリース コードの実行 <br/>- 検疫からのリリース <br/>- 要求サンプル <br/>- コードの実行を制限する (このアクションは元に戻すことができます) <br/>- ウイルス対策スキャンの実行 <br/>- 停止と検疫      |- ブロック URL (クリック時)<br/>- 電子メール メッセージまたはクラスターを論理的に削除する<br/>- 検疫メール<br/>- 電子メールの添付ファイルを検疫する<br/>- 外部メール転送をオフにする          |- ユーザーを無効にする<br />- ユーザー パスワードをリセットする<br />- 侵害されたユーザーを確認する          |

保留中の承認または既に完了しているかどうかに関係なく、修復アクションは [、アクション センター](m365d-action-center.md)で表示できます。

## <a name="remediation-actions-that-follow-automated-investigations"></a>自動調査に続く修復アクション

自動調査が完了すると、関係するすべての証拠について判定に達します。 判定に応じて、修復アクションが識別されます。 修復アクションが自動的に実行される場合もあれば、修復アクションが承認を待機する場合もあります。 すべて [、自動調査と応答の構成](m365d-configure-auto-investigation-response.md)方法によって異なります。

考えられる判定と結果を次の表に示します。

| 判定    | 影響を受けるエンティティ    | 結果|
|------|------|------|
| Malicious (悪意のある)    | デバイス (エンドポイント)    | 修復アクションは自動的に実行されます (組織の [デバイス グループ](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) が [完全] に設定されていると仮定して **脅威を自動的に修復する**)|
| 侵害 | ユーザー | 修復アクションが自動的に実行されます |
| Malicious (悪意のある)    | メールのコンテンツ (URL または添付ファイル) | 推奨される修復アクションが承認待ちになります|
| Suspicious (不審)    | デバイスまたはメールのコンテンツ | 推奨される修復アクションが承認待ちになります|
| 脅威は検出されませんでした    | デバイスまたはメールのコンテンツ    | 必要な修復アクションはありません|

## <a name="remediation-actions-that-are-taken-manually"></a>手動で実行される修復アクション

セキュリティ運用チームは、自動調査に続く修復アクションに加えて、特定の修復アクションを手動で実行できます。 これらには次のコマンドレットがあります。

- デバイスの分離やファイル検疫などの手動デバイス アクション
- メール メッセージの論理的な削除など、手動の電子メール アクション
- ユーザーの無効化やユーザー パスワードのリセットなどの手動ユーザー アクション
- デバイス、ユーザー、または電子メールに対する[高度なハンティング](../defender-endpoint/advanced-hunting-overview.md) アクション
- メール コンテンツに対する[エクスプローラー](../office-365-security/threat-explorer.md) アクション (メールを迷惑メールに移動する、メールを論理的に削除する、メールをハード削除するなど)
- 手動 [のライブ応答](/windows/security/threat-protection/microsoft-defender-atp/live-response) アクション (ファイルの削除、プロセスの停止、スケジュールされたタスクの削除など)
- デバイスの分離、ウイルス対策スキャンの実行、ファイルに関する情報の取得など、[Microsoft Defender for Endpoint API を](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)使用したライブ応答アクション

## <a name="next-steps"></a>次の手順

- [アクション センターにアクセスする](m365d-action-center.md)
- [修復アクションを表示および管理する](m365d-autoir-actions.md)
- [false positives または false negatives に対処する](m365d-autoir-report-false-positives-negatives.md)
