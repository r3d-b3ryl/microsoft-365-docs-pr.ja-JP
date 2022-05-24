---
title: Microsoft Defender for Office 365での修復アクションの確認と管理
keywords: AIR, autoIR, Microsoft Defender for Endpoint, 自動化, 調査, 対応, 修復, 脅威, 高度, 脅威, 保護
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
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
description: Microsoft Defender for Office 365プラン 2 の自動調査と対応機能の修復アクションについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.date: 06/10/2021
ms.openlocfilehash: aaa444a2bada254aeed83540aee361ed806ab0a0
ms.sourcegitcommit: 725a92b0b1555572b306b285a0e7a7614d34e5e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2022
ms.locfileid: "65649123"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Office 365での修復アクションの確認と管理

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 2](defender-for-office-365.md)

電子メール&コラボレーション コンテンツに対する自動調査によって、*悪意や**疑わしい* などの判定が行われると、特定の修復アクションが作成されます。 Microsoft Defender for Office 365では、修復アクションには次のものが含まれます。

- メール メッセージまたはクラスターを論理的に削除する
- 外部メール転送をオフにする

これらの修復アクションは、セキュリティ運用チームが承認しない限り、実行されません。 自動調査が適時に完了するように、できるだけ早く保留中のアクションを確認して承認することをお勧めします。 場合によっては、送信されたアクションを再考できます。  アクションを実行する前に、検索&消去ロールの一部である必要があります。

## <a name="approve-or-reject-pending-actions"></a>保留中のアクションを承認 (または拒否) する

自動調査アクションを見つけて実行するには、次の 4 つの方法があります。

- [インシデント キュー](https://security.microsoft.com/incidents)
- 調査自体 (インシデントまたはアラートからアクセス)
- [アクション センター](https://security.microsoft.com/action-center/pending)
- [調査と修復の調査キュー](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a>インシデント キュー

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**インシデント**] &アラートインシデントの [**インシデント**\>] ページに移動 **します**。 **[インシデント]** ページに直接移動するには、 <https://security.microsoft.com/incidents>.
2. [インシデント] ページ **で** 、インシデント名を選択して概要ページを開きます。
3. [ **証拠と応答** ] タブを選択します。
4. リストからアイテムを選択します。 サイド ウィンドウが開きます。
5. サイド ウィンドウで、承認アクションまたは拒否アクションを実行します。

## <a name="action-center"></a>アクション センター

1. Microsoft 365 Defender ポータルの [<https://security.microsoft.com>**アクション センター**] ページに移動し、[**アクション** センター] を選択します。 **[アクション センター]** ページに直接移動するには、 <https://security.microsoft.com/action-center/pending>.
2. **[アクション センター]** ページで、[**保留中]** タブが選択されていることを確認し、承認を待っているアクションの一覧を確認します。
   - [ **調査を開く] ページ** を選択して、調査の詳細を表示します。
   - [ **承認] を** 選択して保留中のアクションを開始します。
   - 保留中のアクションが実行されないようにするには、[ **拒否] を** 選択します。

## <a name="investigation-and-remediation-investigations-queue"></a>調査と修復の調査キュー

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**電子メール & コラボレーション**\>調査] の **[脅威の調査**] ページに移動 **します**。 **脅威の調査** ページに直接移動するには、<https://security.microsoft.com/airinvestigation>.
2. **[脅威の調査**] ページで、状態が **[保留中] アクション** の一覧からアイテムを検索します。
3. [新しいウィンドウで開く] アイコンをクリック ![します。](../../media/m365-cc-sc-open-icon.png) リスト時刻 (**ID** と **状態** の間) で **新しいウィンドウで開きます**。
4. 開いたページで、承認または拒否のアクションを実行します。

## <a name="change-or-undo-one-remediation-action"></a>1 つの修復アクションを変更または元に戻す

送信されたアクションを再考するには、次の 2 つの方法があります。

- [統合アクション センター](https://security.microsoft.com/action-center)を通じて。
- ただし、[Office アクション センター](https://security.microsoft.com/threatincidents)。

## <a name="change-or-undo-through-the-unified-action-center"></a>統合アクション センターを変更または元に戻す

1. Microsoft 365 Defender ポータルで<https://security.microsoft.com>、アクション センターを選択して統合アクション センターに移動 **します**。 統合アクション センターに直接移動するには、 <https://security.microsoft.com/action-center/>.
2. **[アクション センター]** ページで、[**履歴**] タブを選択し、変更または元に戻すアクションを選択します。
3. 画面の右側にあるウィンドウで、適切なアクション (**受信トレイへの移動**、 **迷惑メールへの移動**、 **削除済みアイテムへの移動**、 **論理的な削除**、 **またはハード削除**) を選択します。

## <a name="change-or-undo-through-the-office-action-center"></a>Office アクション センターを変更または元に戻す

1. Microsoft 365 Defender ポータルで<https://security.microsoft.com>、**電子メール & コラボレーション** \> **レビュー** \> アクション センターのOffice **アクション センター** に移動します。 Office アクション センターに直接移動するには、<https://security.microsoft.com/threatincidents>.
2. **[アクション センター]** ページで、適切な修復を選択します。
3. サイド パネルで、メール送信エントリをクリックし、リストが読み込まれるのを待ちます。
4. 上部の [アクション] ボタンが有効になるまで待ち、[アクション] ボタンを選択してアクションの種類を変更します。
5. これにより、適切なアクションが作成されます。

## <a name="next-steps"></a>次の手順

- [脅威エクスプローラーを使用する](threat-explorer.md)
- [管理/手動操作](remediate-malicious-email-delivered-office-365.md)
- [自動調査と応答機能で誤検知/否定を報告する方法](air-report-false-positives-negatives.md)

## <a name="see-also"></a>関連項目

- [Office 365で自動調査の詳細と結果を表示する](air-view-investigation-results.md)
