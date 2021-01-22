---
title: Microsoft 365 Defender での修復アクション
description: Microsoft 365 Defender での自動調査に従った修復アクションの概要を取得する
keywords: 自動化、調査、警告、トリガー、アクション、修復
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: c6b0275335f32419b470c789d83b069be7839c36
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932852"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Microsoft 365 Defender での修復アクション

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

## <a name="remediation-actions"></a>修復アクション

Microsoft 365 Defender での自動調査の最中および後に、悪意のあるアイテムや疑わしいアイテムに対する修復アクションが特定されます。 一部の種類の修復アクションは、エンドポイントとも呼ばれるデバイスで実行されます。 その他の修復アクションは、メール コンテンツに対して実行されます。 修復アクションが実行、承認、または拒否された後、自動調査が完了します。

> [!IMPORTANT]
> 修復アクションが自動的に実行されるのか、承認によってのみ実行されるのかは、オートメーション レベルなどの特定の設定によって異なります。 詳細については、次の記事を参照してください。
> - [Microsoft 365 Defender で自動調査および対応機能を構成する](mtp-configure-auto-investigation-response.md)
> - [デバイスでの脅威の修復方法](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [コラボレーション コンテンツを含む電子メールに対&と修復アクション](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions#threats-and-remediation-actions)

次の表に、Microsoft 365 Defender で現在サポートされている修復アクションの概要を示します。 

|デバイス (エンドポイント) の修復アクション  |メールの修復アクション  |
|---------|---------|
|- 調査パッケージを収集する <br/>- デバイスを分離する (この操作は元に戻すことができます)<br/>- オフボード コンピューター <br/>- リリース コードの実行 <br/>- 検疫からの解放 <br/>- 要求サンプル <br/>- コードの実行を制限する (この操作は元に戻すことができます) <br/>- ウイルス対策スキャンを実行する <br/>- 停止と検疫      |- URL をブロックする (クリック時)<br/>- メール メッセージまたはクラスターの削除 (回復可能)<br/>- メールを検疫する<br/>- メールの添付ファイルを検疫する<br/>- 外部メール転送を無効にする          |

修復アクションは、承認待ちでも完了済みでも、アクション センターで [表示できます](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)。

## <a name="remediation-actions-that-follow-automated-investigations"></a>自動調査に従う修復アクション

自動調査が完了すると、関係する証拠の一部ごとに 1 つの確認が求めらた。 状況に応じて、修復アクションが識別されます。 修復アクションが自動的に実行される場合もあれば、修復アクションが承認を待機する場合もあります。 すべては、自動調査 [と対応の構成方法によって異なります](mtp-configure-auto-investigation-response.md)。

考えられる判定と結果を次の表に示します。

| 判定    | 分野    | 結果|
|------|------|------|
| Malicious (悪意のある)    | デバイス (エンドポイント)    | 修復アクションが自動的に実行されます (組織の [](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups)デバイス グループが [完全] に設定されている場合 **- 脅威を自動的に修復する**)|
| Malicious (悪意のある)    | メールのコンテンツ (URL または添付ファイル) | 推奨される修復アクションが承認待ちになります|
| Suspicious (不審)    | デバイスまたはメールのコンテンツ | 推奨される修復アクションが承認待ちになります|
| 脅威は検出されませんでした    | デバイスまたはメールのコンテンツ    | 必要な修復アクションはありません|


## <a name="remediation-actions-that-are-taken-manually"></a>手動で実行される修復アクション

自動調査に従う修復アクションに加えて、セキュリティ運用チームは特定の修復アクションを手動で実行できます。 これには、次のアクションが含まれます。

- デバイスの手動による操作 (デバイスの分離やファイル検疫など)。
- 電子メール メッセージのソフト削除など、手動の電子メール アクション。 
- [デバイスまたは電子メール](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) での高度な検索アクション。
- [迷惑](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) メールへのメールの移動、メールのソフト削除、メールのハード削除など、メール コンテンツに対するエクスプローラー アクション。
- ファイル [の削除](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) 、プロセスの停止、スケジュールされたタスクの削除など、手動のライブ応答アクション。
- デバイスの分離、ウイルス対策スキャンの実行、ファイルに関する情報の取得など [、Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)API を使用したライブ応答アクション。 

## <a name="next-steps"></a>次の手順

- [アクション センターにアクセスする](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [保留中のアクションを承認または拒否する](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [自動調査および対応機能で誤検知/陰性を処理する](mtp-autoir-report-false-positives-negatives.md)
