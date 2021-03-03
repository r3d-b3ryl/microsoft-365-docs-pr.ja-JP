---
title: 365 の Microsoft Defender での自動調査に続き、誤検知または誤Officeする方法
description: Microsoft Defender の AIR が 365 で検出した、または誤って検出Officeしましたか? 分析のために誤検知または誤検知を Microsoft に提出する方法について説明します。
keywords: 自動化, 調査, アラート, トリガー, アクション, 修復, 誤検知, 偽陰性
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
ms.technology: mdo
ms.openlocfilehash: 8a91a55d9598b5e780474315ddf1f7019e593fed
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406164"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>自動調査および応答機能で誤検知/陰性を報告する方法

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[Office 365](automated-investigation-response-office.md)の自動調査と応答 (AIR) 機能が何かを見逃した、または誤って検出した場合は、セキュリティ運用チームがそれを修正するために実行できる手順があります。 このようなアクションには、次のものが含まれます。

- [Microsoft に誤検知/陰性を報告する](#report-a-false-positivenegative-to-microsoft-for-analysis)。
- [アラートの調整](#adjust-an-alert-to-prevent-false-positives-from-recurring) (必要な場合)。そして
- [実行された修復アクションの元に戻す](#undo-a-remediation-action)。

この記事をガイドとして使用します。

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>分析のために Microsoft に誤検知/陰性を報告する

microsoft Defender for Office 365 の AIR が電子メール メッセージ、電子メール添付ファイル、電子メール メッセージ内の URL、または Office ファイル内の URL を見逃した場合は、疑わしいスパム、フィッシング、URL、ファイルを microsoft に送信して、Office [365](admin-submission.md)スキャンを行うことができます。

また、マルウェア [分析のためにファイルを Microsoft に送信できます](https://www.microsoft.com/wdsi/filesubmission)。

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>誤検知が繰り返されるのを防ぐためにアラートを調整する

アラートが正当な使用によってトリガーされた場合、またはアラートが不正確な場合は、Cloud App Security ポータルでアラート [を管理できます](https://docs.microsoft.com/cloud-app-security/managing-alerts)。

組織で Office 365 に加えて [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) を使用している場合、ファイル、IP アドレス、URL、またはドメインが安全なデバイス上でマルウェアとして扱われる場合は、デバイスの "許可 ["](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)アクションを使用してカスタム インジケーターを作成できます。

## <a name="undo-a-remediation-action"></a>修復アクションを元に戻す

ほとんどの場合、電子メール メッセージ、電子メール添付ファイル、または URL に対して修復アクションが実行され、アイテムが実際には脅威ではない場合、セキュリティ運用チームは修復アクションを元に戻し、誤検知が繰り返されるのを防ぐための手順を実行できます。 調査に脅威エクスプローラー [または [](#undo-an-action-using-threat-explorer) アクション] タブ [を使用して、アクション](#undo-an-action-in-the-action-center) を元に戻すことができます。

> [!IMPORTANT]
> 次のタスクを実行する前に、必要なアクセス許可を持っている必要があります。

### <a name="undo-an-action-using-threat-explorer"></a>Threat Explorer を使用してアクションを元に戻す

Threat Explorer を使用すると、セキュリティ運用チームは、アクションの影響を受ける電子メールを見つけ、アクションを元に戻す可能性があります。

|シナリオ|元に戻すオプション|詳細情報|
|---|---|---|
|電子メール メッセージがユーザーの迷惑メール フォルダーにルーティングされた|- メッセージをユーザーの [削除済みアイテム] フォルダーに移動する<br/>- メッセージをユーザーの受信トレイに移動する<br/>- メッセージを削除する|[365 で配信された悪意のある電子メールをOfficeする](investigate-malicious-email-that-was-delivered.md)|
|電子メール メッセージまたはファイルが検疫された|- 電子メールまたはファイルを解放する<br/>- 電子メールまたはファイルを削除する|[検疫済みメッセージを管理者として管理する](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a>アクション センターで操作を元に戻す

アクション センターでは、実行された修復アクションを確認し、アクションを元に戻す可能性があります。

1. Microsoft 365 セキュリティ センター ( ) に移動します <https://security.microsoft.com> 。
2. ナビゲーション ウィンドウで、[アクション センター] **を選択します**。
3. [履歴] **タブを** 選択して、完了したアクションの一覧を表示します。
4. アイテムを選択します。 そのフライアウト ウィンドウが開きます。
5. フライアウト ウィンドウで、[元に戻す] を **選択します**。 (元に戻す操作のみ[元に戻 **す]** ボタンがあります)。

## <a name="see-also"></a>関連項目

- [Microsoft Defender for Office 365](office-365-atp.md)
- [Microsoft Defender for Office 365](office-365-air.md)
