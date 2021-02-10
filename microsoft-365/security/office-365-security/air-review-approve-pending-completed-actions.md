---
title: Microsoft Defender for Office 365 での修復アクションの確認と管理
keywords: AIR, autoIR, ATP, 自動化, 調査, 対応, 修復, 脅威, 高度, 脅威, 保護
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
description: Microsoft Defender for Office 365 プラン 2 の自動調査および対応機能の修復アクションについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.date: 01/29/2021
ms.openlocfilehash: 3fb77fa41ff3e9af995cf80b9f4024aa92a51212
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2021
ms.locfileid: "50176017"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Office 365 での修復アクションの確認と管理

メールやグループ作業のコンテンツ&調査を自動化すると、悪意のある、疑わしいなど、特定の修復アクションが作成されます。 Microsoft Defender for Office 365 では、修復アクションには次のものが含まれます。
- URL のブロック (クリック時)
- メール メッセージまたはクラスターのソフト削除
- 電子メールまたはメールの添付ファイルを確認する
- 外部メール転送を無効にする

これらの修復アクションは、セキュリティ運用チームが承認しない限り、実行されるのではありません。 保留中のアクションをできるだけ早く確認して承認し、自動調査が時間内に完了することを推奨します。 場合によっては、修復アクションを元に戻すことができます。

**適用対象**
- [Microsoft Defender for Office 365 プラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="approve-or-reject-pending-actions"></a>保留中のアクションを承認 (または拒否) する

1. Microsoft 365 セキュリティ センターに移動し [https://security.microsoft.com](https://security.microsoft.com) 、サインインします。
2. ナビゲーション ウィンドウで、アクション センターを **選択します**。
3. [ **保留中] タブ** で、承認待ちアクションの一覧を確認します。
4. リストからアイテムを選択します。 そのフライアウト ウィンドウが開きます。 
5. フライアウト ウィンドウで情報を確認し、次のいずれかの手順を実行します。
   - [ **調査を開く] ページを選択** して、調査の詳細を表示します。
   - [ **承認] を** 選択して保留中のアクションを開始します。
   - 保留中 **のアクション** が実行されるのを防ぐには、[拒否] を選択します。

## <a name="undo-one-remediation-action"></a>1 つの修復アクションを元に戻す

1. アクション センター ( ) に移動 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) し、サインインします。
2. [履歴 **] タブ** で、元に戻す操作を選択します。
3. 画面の右側のウィンドウで、[元に戻す] を **選択します**。

## <a name="undo-multiple-remediation-actions"></a>複数の修復操作を元に戻す

1. アクション センター ( ) に移動 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) し、サインインします。
2. [履歴 **] タブ** で、元に戻す操作を選択します。 同じアクションの種類を持つアイテムを選択してください。 フライアウト ウィンドウが開きます。
3. フライアウト ウィンドウで、[元に戻す] を選択します。

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>複数のデバイスにわたる検疫からファイルを削除するには

1. アクション センター ( ) に移動 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) し、サインインします。
2. [履歴 **] タブ** で、操作の種類が検疫ファイルであるファイルを **選択します**。
3. 画面の右側のウィンドウで、[このファイルのインスタンスを **X** に適用する] を選択し、[元に戻す] を選択 **します**。

## <a name="next-steps"></a>次の手順

- [脅威エクスプローラーの使用](threat-explorer.md)
- [自動調査および対応機能で誤検知/陰性を報告する方法](air-report-false-positives-negatives.md)

## <a name="see-also"></a>こちらもご覧ください

- [Office 365 で自動調査の詳細と結果を表示する](air-view-investigation-results.md)
