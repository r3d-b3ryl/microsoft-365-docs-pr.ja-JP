---
title: Microsoft Defender for Office 365の自動調査後に偽陽性または偽陰性を報告する方法
description: Microsoft Defender for Office 365の AIR によって何かが見落とされたか、間違って検出されましたか? 分析のために誤検知または偽陰性を Microsoft に送信する方法について説明します。
keywords: 自動, 調査, アラート, トリガー, アクション, 修復, 偽陽性, 偽陰性
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
ms.service: microsoft-365-security
ms.date: 01/29/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.subservice: mdo
ms.openlocfilehash: 0b48a5d954bb77a8982fa09d03d3acc103973430
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67478665"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>自動調査と応答機能で誤検知/否定を報告する方法

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Office 365の[自動調査と対応 (AIR) 機能で](automated-investigation-response-office.md)何かが見つからないか、間違って検出された場合は、セキュリティ運用チームが修正するために実行できる手順があります。 このようなアクションは次のとおりです。

- [Microsoft に偽陽性/陰性を報告する](#report-a-false-positivenegative-to-microsoft-for-analysis)。
- [アラートの調整](#adjust-an-alert-to-prevent-false-positives-from-recurring) (必要な場合);そして
- [実行された修復アクションを元に戻す](#undo-a-remediation-action)。

この記事をガイドとして使用してください。

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>分析のために Microsoft に誤検知/否定を報告する

メール メッセージ、電子メールの添付ファイル、電子メール メッセージの URL、Office ファイル内の URL が見つからないMicrosoft Defender for Office 365場合は[、疑わしいスパム、フィッシング、URL、ファイルを Microsoft に送信して、スキャンをOffice 365](admin-submission.md)できます。

[マルウェア分析のために Microsoft にファイルを送信](https://www.microsoft.com/wdsi/filesubmission)することもできます。

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>誤検知が繰り返されないようにアラートを調整する

アラートが正当な使用によってトリガーされた場合、またはアラートが不正確な場合は、 [Defender for Cloud Apps ポータルでアラートを管理](/cloud-app-security/managing-alerts)できます。

組織がOffice 365に加えて[Microsoft Defender for Endpoint](/windows/security/threat-protection)を使用していて、ファイル、IP アドレス、URL、またはドメインがデバイス上のマルウェアとして扱われる場合は、安全であっても、[デバイスに対して "許可" アクションを使用してカスタム インジケーターを作成](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)できます。

## <a name="undo-a-remediation-action"></a>修復アクションを元に戻す

ほとんどの場合、電子メール メッセージ、電子メールの添付ファイル、または URL に対して修復アクションが実行され、アイテムが実際には脅威ではない場合、セキュリティ運用チームは修復アクションを元に戻し、誤検知が繰り返されないようにする手順を実行できます。 [調査には、脅威エクスプローラー](#undo-an-action-using-threat-explorer)または [[アクション] タブを](#undo-an-action-in-the-action-center)使用して、アクションを元に戻すことができます。

> [!IMPORTANT]
> 次のタスクを実行する前に、必要なアクセス許可があることを確認してください。

### <a name="undo-an-action-using-threat-explorer"></a>脅威エクスプローラーを使用してアクションを元に戻す

脅威エクスプローラーを使用すると、セキュリティ運用チームは、アクションの影響を受ける電子メールを見つけて、アクションを元に戻す可能性があります。

|シナリオ|[元に戻す] オプション|詳細情報|
|---|---|---|
|ユーザーの迷惑メール Email フォルダーに電子メール メッセージがルーティングされました|<ul><li>メッセージをユーザーの [削除済みアイテム] フォルダーに移動する</li><li>メッセージをユーザーの受信トレイに移動する</li><li>メッセージを削除</li></ul>|[Office 365で配信された悪意のあるメールを検索して調査する](investigate-malicious-email-that-was-delivered.md)|
|電子メール メッセージまたはファイルが検疫されました|<ul><li>電子メールまたはファイルを解放する</li><li> 電子メールまたはファイルを削除する</li></ul>|[検疫済みメッセージを管理者として管理する](manage-quarantined-messages-and-files.md)|

### <a name="undo-an-action-in-the-action-center"></a>アクション センターでアクションを元に戻す

アクション センターでは、実行された修復アクションを確認し、アクションを元に戻す可能性があります。

1. Microsoft 365 Defender ポータルで<https://security.microsoft.com>、アクション センターを選択して **アクション センター** に移動します。 アクション センターに直接移動するには、 <https://security.microsoft.com/action-center/>.
2. アクション センターで [ **履歴** ] タブを選択し、完了したアクションの一覧を表示します。
3. 項目を選択します。 ポップアップ ウィンドウが開きます。
4. ポップアップ ウィンドウで **[元に戻す]** を選択します。 (元に戻すことができる操作にのみ、[ **元に戻す]** ボタンがあります)。

## <a name="see-also"></a>関連項目

- [Microsoft Defender for Office 365](defender-for-office-365.md)
- [Microsoft Defender for Office 365での自動調査](office-365-air.md)
