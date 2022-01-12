---
title: Microsoft Defender で修復アクションを確認および管理Office 365
keywords: AIR、autoIR、Microsoft Defender for Endpoint、自動化、調査、対応、修復、脅威、高度、脅威、保護
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: ''
description: Microsoft Defender for microsoft Defender for Office 365プラン 2 の自動調査および応答機能の修復アクションについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.date: 06/10/2021
ms.openlocfilehash: bc8c99a547e4f30e10575e8353afd6ca02bf233b
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61932775"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>修復アクションを確認および管理Office 365

**適用対象**
- [Microsoft Defender for Office 365 プラン 2](defender-for-office-365.md)

電子メール の自動調査や&コンテンツの結果として、悪意のある、疑わしいなど、特定の修復アクションが作成されます。 Microsoft Defender for Office 365修復アクションには、次のものが含まれます。

- 電子メール メッセージまたはクラスターのソフト削除
- 外部メール転送を無効にする

これらの修復アクションは、セキュリティ運用チームが承認しない限り、実行しません。 保留中のアクションをできるだけ早く確認して承認し、自動化された調査がリアルタイムで完了することを推奨します。 場合によっては、送信されたアクションを再考できます。  アクションを実行する前に、検索&役割の一部である必要があります。

## <a name="approve-or-reject-pending-actions"></a>保留中のアクションを承認 (または拒否) する

自動調査アクションを検索して実行するには、次の 4 つの方法があります。

- [インシデント キュー](https://security.microsoft.com/incidents)
- 調査自体 (インシデントまたはアラートからアクセス)
- [アクション センター](https://security.microsoft.com/action-center/pending)
- [調査と修復の調査キュー](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a>インシデント キュー

1. [インシデント] Microsoft 365 Defenderで、[インシデント] ページに移動し、[インシデント] & <https://security.microsoft.com> **通知** \> **します**。 [インシデント] ページに **直接移動するには、** を使用します <https://security.microsoft.com/incidents> 。
2. [インシデント **] ページで** インシデント名を選択して、概要ページを開きます。
3. [証拠と **応答] タブを選択** します。
4. リストからアイテムを選択します。 サイド ウィンドウが開きます。
5. サイド ウィンドウで、承認または拒否のアクションを実行します。

## <a name="action-center"></a>アクション センター

1. [アクション センター Microsoft 365 Defender] ポータルで、[アクション センター] を選択して <https://security.microsoft.com> [アクション センター]**ページに移動します**。  [アクション センター] ページに **直接移動するには** 、 を使用します <https://security.microsoft.com/action-center/pending> 。
2. [アクション **センター] ページ** で、[ **保留中** ] タブが選択されているのを確認し、承認を待っているアクションの一覧を確認します。
   - [ **調査ページを開く]** を選択して、調査の詳細を表示します。
   - [承認 **] を** 選択して保留中のアクションを開始します。
   - 保留中 **のアクション** が実行されるのを防ぐには、[拒否] を選択します。

## <a name="investigation-and-remediation-investigations-queue"></a>調査と修復の調査キュー

1. [メール] Microsoft 365 Defenderポータルで、[メール] の [脅威の調査] ページに移動し、& <https://security.microsoft.com> **調査** \> **を行います**。 [脅威の調査] ページに直接 **移動するには** 、 を使用します <https://security.microsoft.com/airinvestigation> 。
2. [脅威 **の調査] ページ** で、状態が [保留中] アクションのリストから **アイテムを検索します**。
3. [新 ![ しいウィンドウで開く] アイコンをクリックします。](../../media/m365-cc-sc-open-icon.png) **リストの時刻 (ID と状態** の間) の新しい **ウィンドウ** で **開きます**。
4. 開くページで、承認または拒否のアクションを実行します。

## <a name="change-or-undo-one-remediation-action"></a>1 つの修復アクションを変更または元に戻す

送信されたアクションを再考するには、次の 2 つの方法があります。

- 統合アクション [センターを介して](https://security.microsoft.com/action-center)。
- しかし[、Officeアクション センター](https://security.microsoft.com/threatincidents)です。

## <a name="change-or-undo-through-the-unified-action-center"></a>統合アクション センターで変更または元に戻す

1. [アクション センター Microsoft 365 Defender] ポータルで、[アクション センター] を選択して統合 <https://security.microsoft.com> アクション センター **に移動します**。 統合アクション センターに直接移動するには、 を使用します <https://security.microsoft.com/action-center/> 。
2. [アクション **センター] ページ** で、[履歴] タブ **を** 選択し、変更または元に戻すアクションを選択します。
3. 画面の右側のウィンドウで、適切なアクション **(受信** トレイに移動、迷惑メールへの移動、削除済みアイテムへの移動、ソフト削除、またはハード削除) を選択 **します**。

## <a name="change-or-undo-through-the-office-action-center"></a>変更または元に戻す操作センター Office操作センター

1. [電子メール Microsoft 365 Defender] ポータルで、[メール] グループ Office レビュー アクション センターの <https://security.microsoft.com> **[&]** アクション センター \>  \> **に移動します**。 アクション センターに直接移動するには、Officeを使用します <https://security.microsoft.com/threatincidents> 。
2. [アクション センター **] ページで** 、適切な修復を選択します。
3. サイド パネルで、メール送信エントリをクリックし、リストが読み込むのを待ちます。
4. 上部の [アクション] ボタンが有効なのを待ち、[アクション] ボタンを選択してアクションの種類を変更します。
5. これにより、適切なアクションが作成されます。

## <a name="next-steps"></a>次の手順

- [脅威エクスプローラーの使用](threat-explorer.md)
- [管理者/手動アクション](remediate-malicious-email-delivered-office-365.md)
- [自動調査および応答機能で誤検知/陰性を報告する方法](air-report-false-positives-negatives.md)

## <a name="see-also"></a>関連項目

- [自動調査の詳細と結果を表示Office 365](air-view-investigation-results.md)
