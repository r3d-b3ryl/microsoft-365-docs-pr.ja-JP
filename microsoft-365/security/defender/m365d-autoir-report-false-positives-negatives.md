---
title: ユーザーの誤検知または誤検知に対処Microsoft 365 Defender
description: AIR によって検出された、または誤って検出されたMicrosoft 365 Defender? 分析のために誤検知または誤検知を Microsoft に提出する方法について説明します。
keywords: 自動化、調査、アラート、修復、誤検知、偽陰性
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: df2effa41977624530b5f9ea8881f7f5aaeef82f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60209107"
---
# <a name="address-false-positives-or-false-negatives-in-microsoft-365-defender"></a>ユーザーの誤検知または誤検知に対処Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

脅威保護ソリューションでは、誤検知や陰性が発生することがあります。 自動[調査および応答](m365d-autoir.md)機能がMicrosoft 365 Defenderまたは誤って検出された場合、セキュリティ運用チームが実行できる手順は次のとおりです。

- [Microsoft に誤検知/陰性を報告する](#report-a-false-positivenegative-to-microsoft-for-analysis)
- [アラートを調整](#adjust-an-alert-to-prevent-false-positives-from-recurring) する (必要な場合)
- [デバイスで実行された修復アクションを元に戻す](#undo-a-remediation-action-that-was-taken-on-a-device)

以下のセクションでは、これらのタスクを実行する方法について説明します。

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>分析のために Microsoft に誤検知/陰性を報告する

|アイテムが見つからないか、誤って検出された |サービス  |操作  |
|---------|---------|---------|
|- 電子メール メッセージ <br/>- メールの添付ファイル <br/>- 電子メール メッセージの URL<br/>- ファイル内の URL Officeファイル      |[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)        |[疑わしいスパム、フィッシング、URL、ファイルをスキャンのために Microsoft に送信する](../office-365-security/admin-submission.md)         |
|デバイス上のファイルまたはアプリ    |[Microsoft Defender for Endpoint](/windows/security/threat-protection)         |[マルウェア分析のために Microsoft にファイルを送信する](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>誤検知が繰り返されるのを防ぐためにアラートを調整する

|シナリオ |サービス |操作 |
|--------|--------|--------|
|- アラートは正当な使用によってトリガーされます <br/>- アラートが不正確    |[Microsoft Cloud App Security](/cloud-app-security)<br/> または <br/>[Azure の脅威保護](/azure/security/fundamentals/threat-detection)         |[ポータルでアラートをCloud App Securityする](/cloud-app-security/managing-alerts)         |
|ファイル、IP アドレス、URL、またはドメインは、安全なデバイス上のマルウェアとして扱われる|[Microsoft Defender for Endpoint](/windows/security/threat-protection) |["許可" アクションを使用してカスタム インジケーターを作成する](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>デバイスで実行された修復アクションを元に戻す

エンティティ (デバイスや電子メール メッセージなど) に対して修復アクションが実行され、影響を受けるエンティティが実際には脅威ではない場合、セキュリティ運用チームはアクション センターで修復[](m365d-action-center.md)アクションを元に戻すことができます。

1. [https://security.microsoft.com](https://security.microsoft.com) に移動し、サインインします。 
2. ナビゲーション ウィンドウで、[**アクション センター**] を選択します。 
3. [履歴 **] タブ** で、元に戻す操作を選択します。 そのフライアウト ウィンドウが開きます。
4. フライアウト ウィンドウで、[元に戻す] を **選択します**。

> [!TIP]
> 「完了 [した操作を元に戻す」を参照してください](m365d-autoir-actions.md#undo-completed-actions)。

## <a name="see-also"></a>関連項目

- [自動調査の詳細と結果を表示する](m365d-autoir-results.md)
- [高度な検索機能を使用して、脅威を事前に検出Microsoft 365 Defender](advanced-hunting-overview.md)
