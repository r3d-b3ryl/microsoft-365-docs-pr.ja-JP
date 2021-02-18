---
title: Microsoft Defender で自動調査を行った後、誤検知または検出検出を報告する方法 (Office 365)
description: Microsoft Defender for Office 365 で AIR によって検出された何かが見つからないか、誤って検出されましたか? 分析のために誤検知または検出検出を Microsoft に送信する方法について説明します。
keywords: 自動化, 調査, アラート, トリガー, アクション, 修復, 誤検知, 検出検出
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
ms.openlocfilehash: 48d7e1a7497f9bc2a07a84b36fb07939d25609bf
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289151"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>自動調査および対応機能で誤検知/陰性を報告する方法

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[Office 365](automated-investigation-response-office.md)の自動調査および対応 (AIR) 機能で何かが見つからないか、誤って検出された場合は、セキュリティ運用チームが修正手順を実行できます。 このようなアクションには、次のものが含まれます。

- [Microsoft に誤検知/陰性を報告する](#report-a-false-positivenegative-to-microsoft-for-analysis)。
- [アラートの調整](#adjust-an-alert-to-prevent-false-positives-from-recurring) (必要な場合)そして
- [実行された修復アクションを元に戻す](#undo-a-remediation-action)。

この記事をガイドとして使用します。

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>誤検知/陰性を分析のために Microsoft に報告する

Office 365 用 Microsoft Defender の AIR がメール メッセージ、電子メール添付ファイル、電子メール メッセージ内の URL、または Office ファイル内の URL を見逃した場合は、スパム、フィッシング、URL、ファイルの疑いがあるファイルを [Office 365](admin-submission.md)スキャンのために Microsoft に送信できます。

マルウェア分析 [のために Microsoft にファイルを送信することができます](https://www.microsoft.com/wdsi/filesubmission)。

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>誤検知が繰り返されるのを防ぐためにアラートを調整する

警告が正当な使用によってトリガーされた場合、またはアラートが不正確な場合は、Cloud App Security ポータルでアラート [を管理できます](https://docs.microsoft.com/cloud-app-security/managing-alerts)。

組織で Office 365 に加えて [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) を使用している場合、安全なデバイスでもファイル、IP アドレス、URL、またはドメインがマルウェアとして扱われる場合は、デバイスに対して "許可 ["](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)アクションを使用してカスタム インジケーターを作成できます。

## <a name="undo-a-remediation-action"></a>修復アクションを元に戻す

ほとんどの場合、メール メッセージ、電子メールの添付ファイル、または URL に対して修復アクションが実行され、アイテムが実際には脅威ではない場合、セキュリティ運用チームは修復アクションを元に戻し、誤検知が繰り返し発生しなからなを防ぐための手順を実行できます。 脅威エクスプローラーまたは [ [操作](#undo-an-action-using-threat-explorer) ] タブを使用して調査を [行](#undo-an-action-in-the-action-center) い、操作を元に戻すことができます。

> [!IMPORTANT]
> 次のタスクを実行する前に、必要なアクセス許可を持っている必要があります。

### <a name="undo-an-action-using-threat-explorer"></a>脅威エクスプローラーを使用して操作を元に戻す

脅威エクスプローラーを使用すると、セキュリティ運用チームはアクションの影響を受ける電子メールを見つけ、アクションを元に戻す可能性があります。

|シナリオ|元に戻すオプション|詳細情報|
|---|---|---|
|ユーザーの迷惑メール フォルダーにメール メッセージがルーティングされた|- メッセージをユーザーの [削除済みアイテム] フォルダーに移動する<br/>- メッセージをユーザーの受信トレイに移動する<br/>- メッセージを削除する|[Office 365 で配信された悪意のあるメールを検索して調査する](investigate-malicious-email-that-was-delivered.md)|
|メール メッセージまたはファイルが検疫された|- 電子メールまたはファイルを解放する<br/>- メールまたはファイルを削除する|[管理者として検疫済みメッセージを管理する](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a>アクション センターで操作を元に戻す

アクション センターでは、実行された修復アクションを確認し、アクションを元に戻す可能性があります。

1. Microsoft 365 セキュリティ センター ( ) に移動します [https://security.microsoft.com](https://security.microsoft.com) 。
2. ナビゲーション ウィンドウで、アクション センターを **選択します**。 
3. 完了した **アクションの** 一覧を表示するには、[履歴] タブを選択します。
4. アイテムを選択します。 そのフライアウト ウィンドウが開きます。 
5. フライアウト ウィンドウで、[元に戻す] を **選択します**。 (元に戻す操作のみを元に戻すボタンがあります。

## <a name="see-also"></a>関連項目

- [Microsoft Defender for Office 365](office-365-atp.md)
- [Microsoft Defender for Office 365 での自動調査](office-365-air.md)
