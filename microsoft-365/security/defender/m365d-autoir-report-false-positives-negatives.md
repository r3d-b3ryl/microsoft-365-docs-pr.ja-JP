---
title: Microsoft 365 Defenderの誤検知または偽陰性に対処する
description: Microsoft 365 Defenderで AIR によって何かが見落とされたか、間違って検出されましたか? 分析のために誤検知または偽陰性を Microsoft に送信する方法について説明します。
keywords: 自動, 調査, アラート, 修復, 偽陽性, 偽陰性
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.topic: how-to
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
ms.openlocfilehash: cab16efa7f5118a4b9fce44713536dc043dd6b7b
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482386"
---
# <a name="address-false-positives-or-false-negatives-in-microsoft-365-defender"></a>Microsoft 365 Defenderの誤検知または偽陰性に対処する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

脅威保護ソリューションでは、偽陽性または陰性が発生する場合があります。 Microsoft 365 Defenderの[自動調査と対応機能](m365d-autoir.md)で何かが見つからないか、間違って検出された場合は、セキュリティ運用チームが実行できる手順があります。

- [Microsoft に偽陽性/陰性を報告する](#report-a-false-positivenegative-to-microsoft-for-analysis)
- [アラートを調整する](#adjust-an-alert-to-prevent-false-positives-from-recurring) (必要な場合)
- [デバイスで実行された修復操作を元に戻す](#undo-a-remediation-action-that-was-taken-on-a-device)

次のセクションでは、これらのタスクを実行する方法について説明します。

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>分析のために Microsoft に誤検知/否定を報告する

|アイテムが見落とされたか、間違って検出されました |サービス  |操作  |
|---------|---------|---------|
|- Email メッセージ <br/>- 添付ファイルをEmailする <br/>- 電子メール メッセージ内の URL<br/>- Office ファイル内の URL      |[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)        |[疑わしいスパム、フィッシング、URL、ファイルを Microsoft に送信してスキャンする](../office-365-security/admin-submission.md)         |
|デバイス上のファイルまたはアプリ    |[Microsoft Defender for Endpoint](/windows/security/threat-protection)         |[マルウェア分析のために Microsoft にファイルを送信する](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>誤検知が繰り返されないようにアラートを調整する

|シナリオ |サービス |操作 |
|--------|--------|--------|
|- 正当な使用によってアラートがトリガーされる <br/>- アラートが不正確である    |[Microsoft Defender for Cloud Apps](/cloud-app-security)<br/> or <br/>[Azure の脅威の保護](/azure/security/fundamentals/threat-detection)         |[Defender for Cloud Apps ポータルでアラートを管理する](/cloud-app-security/managing-alerts)         |
|ファイル、IP アドレス、URL、またはドメインは、安全であってもデバイス上のマルウェアとして扱われます|[Microsoft Defender for Endpoint](/windows/security/threat-protection) |["Allow" アクションを使用してカスタム インジケーターを作成する](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>デバイスで実行された修復アクションを元に戻す

エンティティ (デバイスや電子メール メッセージなど) に対して修復アクションが実行され、影響を受けるエンティティが実際には脅威ではない場合、セキュリティ運用チームは [アクション センター](m365d-action-center.md)で修復アクションを元に戻すことができます。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>に移動し、サインインします。 
2. ナビゲーション ウィンドウで、[**アクション センター**] を選択します。 
3. **[履歴]** タブで、元に戻す処理を選択します。 ポップアップ ウィンドウが開きます。
4. ポップアップ ウィンドウで **[元に戻す]** を選択します。

> [!TIP]
> [完了した操作を元に戻す](m365d-autoir-actions.md#undo-completed-actions)を参照してください。

## <a name="see-also"></a>関連項目

- [自動調査の詳細と結果を表示する](m365d-autoir-results.md)
- [Microsoft 365 Defender の高度な捜索により、脅威を積極的に捜索する](advanced-hunting-overview.md)
