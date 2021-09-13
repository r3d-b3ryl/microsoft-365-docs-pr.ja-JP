---
title: Microsoft Defender で自動調査を行った後に、誤検知または誤検知を報告するOffice 365
description: Microsoft Defender で AIR によって検出された、または誤って検出されたデータOffice 365? 分析のために誤検知または誤検知を Microsoft に提出する方法について説明します。
keywords: 自動化, 調査, アラート, トリガー, アクション, 修復, 誤検知, 偽陰性
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
ms.prod: m365-security
ms.date: 01/29/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 287bd9cd4dda6ccb152e93908a409e036eab9cc7
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59219904"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>自動調査および応答機能で誤検知/陰性を報告する方法

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Office 365の自動調査と応答[(AIR)](automated-investigation-response-office.md)機能が何かを見逃したり誤って検出したりした場合は、セキュリティ運用チームがそれを修正する手順があります。 このようなアクションには、次のものが含まれます。

- [Microsoft に誤検知/陰性を報告する](#report-a-false-positivenegative-to-microsoft-for-analysis)。
- [アラートの調整](#adjust-an-alert-to-prevent-false-positives-from-recurring) (必要な場合)。そして
- [実行された修復アクションの元に戻す](#undo-a-remediation-action)。

この記事をガイドとして使用します。

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>分析のために Microsoft に誤検知/陰性を報告する

microsoft Defender for Office 365 の AIR で電子メール メッセージ、電子メール添付ファイル、電子メール メッセージ内の URL、または Office ファイル内の URL が見つからない場合は、疑わしいスパム、フィッシング[、URL、](admin-submission.md)ファイルを microsoft に送信して、Office 365 スキャンを行うことができます。

また、マルウェア [分析のためにファイルを Microsoft に送信できます](https://www.microsoft.com/wdsi/filesubmission)。

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>誤検知が繰り返されるのを防ぐためにアラートを調整する

アラートが正当な使用によってトリガーされた場合、またはアラートが不正確な場合は、ポータルでアラートを[Cloud App Securityできます](/cloud-app-security/managing-alerts)。

組織が Office 365 に加えて[Microsoft Defender for Endpoint](/windows/security/threat-protection)を使用している場合、ファイル、IP アドレス、URL、またはドメインが安全なデバイス上でマルウェアとして扱われる場合は、デバイスの "許可["](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)アクションを使用してカスタム インジケーターを作成できます。

## <a name="undo-a-remediation-action"></a>修復アクションを元に戻す

ほとんどの場合、電子メール メッセージ、電子メール添付ファイル、または URL に対して修復アクションが実行され、アイテムが実際には脅威ではない場合、セキュリティ運用チームは修復アクションを元に戻し、誤検知が繰り返されるのを防ぐための手順を実行できます。 調査に脅威エクスプローラー [または [](#undo-an-action-using-threat-explorer) アクション] タブ [を使用して、アクション](#undo-an-action-in-the-action-center) を元に戻すことができます。

> [!IMPORTANT]
> 次のタスクを実行する前に、必要なアクセス許可を持っている必要があります。

### <a name="undo-an-action-using-threat-explorer"></a>Threat Explorer を使用してアクションを元に戻す

Threat Explorer を使用すると、セキュリティ運用チームは、アクションの影響を受ける電子メールを見つけ、アクションを元に戻す可能性があります。

<br>

****

|シナリオ|元に戻すオプション|詳細情報|
|---|---|---|
|電子メール メッセージがユーザーの迷惑メール フォルダーにルーティングされた|<ul><li>メッセージをユーザーの [削除済みアイテム] フォルダーに移動する</li><li>メッセージをユーザーの受信トレイに移動する</li><li>メッセージを削除</li></ul>|[ネットワークで配信された悪意のある電子メールを検索してOffice 365](investigate-malicious-email-that-was-delivered.md)|
|電子メール メッセージまたはファイルが検疫された|<ul><li>電子メールまたはファイルを解放する</li><li> 電子メールまたはファイルを削除する</li></ul>|[検疫済みメッセージを管理者として管理する](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a>アクション センターで操作を元に戻す

アクション センターでは、実行された修復アクションを確認し、アクションを元に戻す可能性があります。

1. [ポータル] () Microsoft 365 Defender移動します <https://security.microsoft.com> 。
2. ナビゲーション ウィンドウで、[アクション センター] **を選択します**。
3. [履歴] **タブを** 選択して、完了したアクションの一覧を表示します。
4. アイテムを選択します。 そのフライアウト ウィンドウが開きます。
5. フライアウト ウィンドウで、[元に戻す] を **選択します**。 (元に戻す操作のみ[元に戻 **す]** ボタンがあります)。

## <a name="see-also"></a>関連項目

- [Microsoft Defender for Office 365](defender-for-office-365.md)
- [Microsoft Defender での自動調査によるOffice 365](office-365-air.md)
