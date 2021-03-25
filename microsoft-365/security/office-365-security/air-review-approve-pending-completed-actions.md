---
title: Microsoft Defender for microsoft Defender の修復アクションを確認および管理Office 365
keywords: AIR、autoIR、ATP、自動化、調査、対応、修復、脅威、高度、脅威、保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft Defender for microsoft Defender for 365 Plan 2 のOffice修復アクションについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.date: 01/29/2021
ms.openlocfilehash: 61e9df45419cc73dae27b86dad47e1938183593d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205146"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>365 で修復アクションを確認Officeする

電子メール の自動調査や&コンテンツの結果として、悪意のある、疑わしいなど、特定の修復アクションが作成されます。 Microsoft Defender for Office 365 では、修復アクションには次のものが含まれます。
- URL のブロック (クリック時)
- 電子メール メッセージまたはクラスターのソフト削除
- メールまたはメールの添付ファイルを Quarantining する
- 外部メール転送を無効にする

これらの修復アクションは、セキュリティ運用チームが承認しない限り、実行しません。 保留中のアクションをできるだけ早く確認して承認し、自動化された調査がリアルタイムで完了することを推奨します。 場合によっては、修復アクションを元に戻すことができます。

**適用対象**
- [Microsoft Defender for Office 365 プラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="approve-or-reject-pending-actions"></a>保留中のアクションを承認 (または拒否) する

1. Microsoft 365 セキュリティ センター ( ) に移動し <https://security.microsoft.com> 、サインインします。
2. ナビゲーション ウィンドウで、[アクション センター] **を選択します**。
3. [保留中 **] タブ** で、承認を待っているアクションの一覧を確認します。
4. リストからアイテムを選択します。 そのフライアウト ウィンドウが開きます。 
5. フライアウト ウィンドウで情報を確認し、次のいずれかの手順を実行します。
   - [ **調査ページを開く]** を選択して、調査の詳細を表示します。
   - [承認 **] を** 選択して保留中のアクションを開始します。
   - 保留中 **のアクション** が実行されるのを防ぐには、[拒否] を選択します。

## <a name="undo-one-remediation-action"></a>1 つの修復アクションを元に戻す

1. アクション センター ( ) に移動 <https://security.microsoft.com/action-center> し、サインインします。
2. [履歴 **] タブ** で、元に戻す操作を選択します。
3. 画面の右側のウィンドウで、[元に戻す] を **選択します**。

## <a name="undo-multiple-remediation-actions"></a>複数の修復アクションを元に戻す

1. アクション センター ( ) に移動 <https://security.microsoft.com/action-center> し、サインインします。
2. [履歴 **] タブ** で、元に戻す操作を選択します。 同じアクションの種類を持つアイテムを選択してください。 フライアウト ウィンドウが開きます。
3. フライアウト ウィンドウで、[元に戻す] を選択します。

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>複数のデバイス間で検疫からファイルを削除するには

1. アクション センター ( ) に移動 <https://security.microsoft.com/action-center> し、サインインします。
2. [履歴 **] タブ** で、アクションの種類が [検疫ファイル] のファイルを **選択します**。
3. 画面の右側のウィンドウで、[このファイルのインスタンスを **X** に適用する] を選択し、[元に戻す] を **選択します**。

## <a name="next-steps"></a>次の手順

- [脅威エクスプローラーの使用](threat-explorer.md)
- [自動調査および応答機能で誤検知/陰性を報告する方法](air-report-false-positives-negatives.md)

## <a name="see-also"></a>関連項目

- [365 で自動調査の詳細と結果Officeする](air-view-investigation-results.md)
