---
title: Office 365 の誤検知または誤検知を報告する方法自動調査と応答
description: Office 365 Advanced Threat Protection によって失われた、または誤って検出されたものがあるか。 分析のために誤検知または誤検知を Microsoft に送信する方法について説明します。
keywords: 自動化、調査、警告、トリガー、アクション、修復、誤検知、false 負
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 05/15/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 2dd67af62a400f3e217f146e6d0ee213d74ad99a
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262416"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>自動調査および応答機能の誤検知/ネガを報告する方法

**適用対象:**
- Office 365 Advanced Threat Protection

[Office 365 ミスの自動化された調査と応答 (AIR) 機能](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)が、誤って検出されたのでしょうか。 この問題を解決するには、以下の手順を実行します。 以下のことを実行できます。
- [False 正/負の値を Microsoft に報告し](#report-a-false-positivenegative-to-microsoft-for-analysis)ます。
- [通知を調整し](#adjust-an-alert-to-prevent-false-positives-from-recurring)ます (必要な場合)。そして 
- [デバイスに対して実行された修復操作を元に戻し](#undo-a-remediation-action)ます。 

この記事をガイドとして使用します。 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>False 正/負の値を分析のために Microsoft に報告する

Office 365 AIR で不在着信した電子メールメッセージ、電子メールの添付ファイル、電子メールメッセージ内の URL、または Office ファイル内の URL は、[フィッシングのスパム、、url、およびファイルを Microsoft For office 365 のスキャンに送信](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)できます。

また[、マルウェア分析のために Microsoft にファイルを送信](https://www.microsoft.com/wdsi/filesubmission)することもできます。

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>警告を調整して誤検知が繰り返されないようにする

正当な使用によって警告がトリガーされた場合、または警告が不正確な場合は、 [Cloud App Security ポータルで通知を管理](https://docs.microsoft.com/cloud-app-security/managing-alerts)できます。

Office 365 に加えて、組織で[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection)を使用していて、ファイル、IP アドレス、URL、またはドメインがデバイスでマルウェアとして扱われている場合、そのファイル、IP アドレス、URL、またはドメインは、安全であっても、[デバイスの "許可" アクションを含むカスタムインジケーターを作成](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)できます。

## <a name="undo-a-remediation-action"></a>修復アクションを元に戻す

ほとんどの場合、ウイルス対策アクションが電子メールメッセージ、電子メールの添付ファイル、または URL に対して実行され、そのアイテムが実際には脅威ではない場合、セキュリティ操作チームは修復アクションを取り消すことができ、誤検知が定期的に行われないようにするための手順を実行することができます。 操作を取り消すには、[脅威エクスプローラー](#undo-an-action-using-threat-explorer)または [[操作] タブ](#undo-an-action-using-the-actions-tab-for-an-investigation)を使用して調査を行うことができます。 

> [!IMPORTANT]
> 次のタスクを実行する前に、必要なアクセス許可があることを確認してください。

### <a name="undo-an-action-using-threat-explorer"></a>脅威エクスプローラーを使用してアクションを元に戻す

脅威エクスプローラーを使用すると、セキュリティ運用チームは、アクションによって影響を受ける電子メールを検索し、アクションを元に戻す可能性があります。

|シナリオ  |元に戻すオプション  |詳細情報 |
|---------|---------|---------|
|電子メールメッセージがユーザーの迷惑メールフォルダーにルーティングされた     |-ユーザーの削除済みアイテムフォルダーにメッセージを移動する<br/>-ユーザーの受信トレイにメッセージを移動する <br/>-メッセージを削除する          |[Office 365 で配信された悪意のある電子メールを検索して調査する](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered) |
|電子メールメッセージまたはファイルが検疫された     |-電子メールまたはファイルを解放します。 <br/>-電子メールまたはファイルを削除します。         |[Office 365 の管理者として検疫済みメッセージおよびファイルを管理する](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files) |


### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a>[操作] タブを使用して、調査を行うアクションを元に戻す

アクションセンターでは、実行された修復アクションを確認し、アクションを元に戻す可能性があります。

1. [https://protection.office.com](https://protection.office.com) に移動し、サインインします。 これにより、セキュリティ & コンプライアンスセンターに移動できます。

2. [**脅威管理**  >  の**調査**] に移動します。

3. 調査の一覧で、アイテムの ID の横にある [**新しいウィンドウで開く**] アイコンを選択します。

4. [**操作**] タブを選択します。

5. 状態が [**完了**] であるアイテムを選択し、[**判断**] 列で [**承認済み**] などのリンクを探します。 これにより、アクションの詳細を含むフライアウトが開きます。

6. アクションを元に戻すには、[**修復の削除**] を選択します。

## <a name="related-articles"></a>関連記事

[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[Office 365 で自動調査と応答 (AIR) の使用を開始する](office-365-air.md)