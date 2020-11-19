---
title: Microsoft Defender for Office 365 で自動調査を行った後の誤検知または誤否定を報告する方法
description: Office 365 の Microsoft Defender で、何らかの問題があるか、空軍によって誤って検出されましたか? 分析のために誤検知または誤検知を Microsoft に送信する方法について説明します。
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
ms.date: 09/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: conceptual
ms.custom:
- autoir
ms.openlocfilehash: 27edc44145e7b61768d9caf00a3f308e8561d708
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357401"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>自動調査および応答機能の誤検知/ネガを報告する方法

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**適用対象:**
- Microsoft Defender for Office 365

[Office 365 ミスの自動化された調査と応答 (AIR) 機能](automated-investigation-response-office.md)が、誤って検出されたのでしょうか。 この問題を解決するには、以下の手順を実行します。 次の操作を行うことができます:

- [False 正/負の値を Microsoft に報告し](#report-a-false-positivenegative-to-microsoft-for-analysis)ます。
- [通知を調整し](#adjust-an-alert-to-prevent-false-positives-from-recurring) ます (必要な場合)。そして
- [実行された修復操作を元に戻し](#undo-a-remediation-action)ます。

この記事をガイドとして使用します。

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>False 正/負の値を分析のために Microsoft に報告する

Microsoft Defender for Office 365 で、電子メールメッセージ、電子メールの添付ファイル、電子メールメッセージ内の URL、または Office ファイルの URL のいずれかが失われた場合は、 [フィッシング、url、およびファイルを microsoft For office 365 のスキャンに送信](admin-submission.md)できます。

また [、マルウェア分析のために Microsoft にファイルを送信](https://www.microsoft.com/wdsi/filesubmission)することもできます。

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>警告を調整して誤検知が繰り返されないようにする

正当な使用によって警告がトリガーされた場合、または警告が不正確な場合は、 [Cloud App Security ポータルで通知を管理](https://docs.microsoft.com/cloud-app-security/managing-alerts)できます。

Office 365 に加えて、 [エンドポイントに Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) を使用している組織で、ファイル、IP アドレス、URL、またはドメインがデバイスでマルウェアとして扱われている場合は、そのデバイス [の "許可" アクションを使用してカスタムインジケーターを作成](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)できます。

## <a name="undo-a-remediation-action"></a>修復アクションを元に戻す

ほとんどの場合、ウイルス対策アクションが電子メールメッセージ、電子メールの添付ファイル、または URL に対して実行され、そのアイテムが実際には脅威ではない場合、セキュリティ操作チームは修復アクションを取り消すことができ、誤検知が定期的に行われないようにするための手順を実行することができます。 操作を取り消すには、 [脅威エクスプローラー](#undo-an-action-using-threat-explorer) または [ [操作] タブ](#undo-an-action-using-the-actions-tab-for-an-investigation) を使用して調査を行うことができます。

> [!IMPORTANT]
> 次のタスクを実行する前に、必要なアクセス許可があることを確認してください。

### <a name="undo-an-action-using-threat-explorer"></a>脅威エクスプローラーを使用してアクションを元に戻す

脅威エクスプローラーを使用すると、セキュリティ運用チームは、アクションによって影響を受ける電子メールを検索し、アクションを元に戻す可能性があります。

****

|シナリオ|元に戻すオプション|詳細情報|
|---|---|---|
|電子メールメッセージがユーザーの迷惑メールフォルダーにルーティングされた|<ul><li>メッセージをユーザーの削除済みアイテムフォルダーに移動する</li><li>ユーザーの受信トレイにメッセージを移動する</li><li>メッセージを削除</li></ul>|[Office 365 で配信された悪意のある電子メールを検索して調査する](investigate-malicious-email-that-was-delivered.md)|
|電子メールメッセージまたはファイルが検疫された|<ul><li>メールまたはファイルを解放する</li><li>メールまたはファイルを削除する</li></ul>|[管理者として検疫済みメッセージを管理する](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a>[操作] タブを使用して、調査を行うアクションを元に戻す

アクションセンターでは、実行された修復アクションを確認し、アクションを元に戻す可能性があります。

1. [https://protection.office.com](https://protection.office.com) に移動し、サインインします。 これにより、セキュリティ & コンプライアンスセンターに移動できます。

2. [**脅威管理**  >  の **調査**] に移動します。

3. 調査の一覧で、アイテムの ID の横にある [ **新しいウィンドウで開く** ] アイコンを選択します。

4. [ **操作** ] タブを選択します。

5. 状態が [**完了**] であるアイテムを選択し、[**判断**] 列で [**承認済み**] などのリンクを探します。 これにより、アクションの詳細を含むフライアウトが開きます。

6. アクションを元に戻すには、[ **修復の削除**] を選択します。

## <a name="related-articles"></a>関連記事

[Microsoft Defender for Office 365](office-365-atp.md)

[Microsoft Defender for Office 365 の空気](office-365-air.md)
