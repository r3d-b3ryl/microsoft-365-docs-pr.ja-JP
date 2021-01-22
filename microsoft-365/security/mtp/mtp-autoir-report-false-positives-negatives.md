---
title: Microsoft 365 Defender で AIR で誤検知または検出検出を処理する
description: Microsoft 365 Defender で AIR によって何かが見つからないか、誤って検出されましたか? 分析のために誤検知または検出検出を Microsoft に送信する方法について説明します。
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
ms.date: 09/16/2020
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
ms.openlocfilehash: dbef240e28258d1ac4000c05538d0ce073a9d910
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930356"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>自動調査および対応機能で誤検知/陰性を処理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

Microsoft [](mtp-autoir.md) 365 Defender の自動調査および対応機能は、何かを検出したのか、間違って検出されましたか? この問題を解決するには、次の手順を実行できます。 以下のことを実行できます。

- [誤検知/陰性を Microsoft に報告します](#report-a-false-positivenegative-to-microsoft-for-analysis)。

- [アラートを調整](#adjust-an-alert-to-prevent-false-positives-from-recurring) する (必要な場合)。そして 

- [デバイスで実行された修復操作を元に戻します](#undo-a-remediation-action-that-was-taken-on-a-device)。 

この記事をガイドとして使用します。 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>誤検知/陰性を分析のために Microsoft に報告する

|アイテムが見つからないか誤って検出された |サービス  |操作  |
|---------|---------|---------|
|- 電子メール メッセージ <br/>- 電子メールの添付ファイル <br/>- 電子メール メッセージの URL<br/>- ファイル内Office URL      |[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[疑わしいスパム、フィッシング、URL、ファイルをスキャンのために Microsoft に送信する](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|デバイス上のファイルまたはアプリ    |[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection)         |[マルウェア分析のために Microsoft にファイルを送信する](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>誤検知が繰り返されるのを防ぐためにアラートを調整する

|シナリオ |サービス |操作 |
|--------|--------|--------|
|- アラートは正当な使用によってトリガーされます <br/>- アラートが不正確    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> または <br/>[Azure Advanced Threat Detection](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Cloud App Security ポータルでアラートを管理する](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|ファイル、IP アドレス、URL、またはドメインは、安全なデバイスではマルウェアとして扱われる|[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) |["許可" アクションを使用してカスタム インジケーターを作成する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>デバイスで実行された修復アクションを元に戻す

修復アクションがデバイス (Windows 10 デバイスなど) で実行され、アイテムが実際には脅威ではない場合、セキュリティ運用チームはアクション センターで修復アクションを元に戻[すことができます。](mtp-action-center.md)

> [!IMPORTANT]
> 次のタスクを実行 [する前に](mtp-action-center.md#required-permissions-for-action-center-tasks) 、必要なアクセス許可を持っている必要があります。

1. [https://security.microsoft.com](https://security.microsoft.com) に移動し、サインインします。 

2. ナビゲーション ウィンドウで、[**アクション センター**] を選択します。 

3. [履歴 **]** タブで、元に戻す操作を選択します。 これにより、フライアウトが開きます。<br/>
    > [!TIP]
    > フィルターを使用して結果の一覧を絞り込む。 

4. 選択した項目のフライアウトで、[調査ページを開く] **を選択します**。

5. 調査の詳細ビューで、[操作] タブ **を選択** します。

6. 状態が [完了]のアイテムを選択し、[決定] 列で[承認済み] などのリンク **を探** します。 これにより、アクションの詳細を含むフライアウトが開きます。

7. 操作を元に戻すには、[修復の削除] **を選択します**。

## <a name="see-also"></a>関連項目

- [自動調査の詳細と結果を表示する](mtp-autoir-results.md)
- [Microsoft 365 Defender で高度な検索を使用して脅威を事前に探す](advanced-hunting-overview.md)
