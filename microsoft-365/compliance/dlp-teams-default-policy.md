---
title: Microsoft Teams の既定のデータ損失防止ポリシー (プレビュー) について説明します。
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Microsoft Teams の既定のデータ損失防止ポリシーについて説明します。
ms.openlocfilehash: 3992daf9431dbd87ed5e947a1e5a2b0acd20edce
ms.sourcegitcommit: 450661071e44854f0a0a92af648f76d907767b71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "50826248"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a>Microsoft Teams の既定のデータ損失防止ポリシー (プレビュー) について説明します。

[データ損失防止](data-loss-prevention-policies.md) (DLP) 機能が拡張され、Microsoft Teams のチャット メッセージとチャネル メッセージ (プライベート チャネル メッセージを含む) が含まれます。 このリリースの一環として、コンプライアンス センターに初めてお客様向け既定の DLP ポリシーを作成しました。

## <a name="applies-to"></a>適用対象

以下の 1 つ以上のライセンスでライセンスを取得し、アクティブな Teams ユーザーを持つテナント
 
- ME5, 
- MA5, 
- E5/A5 コンプライアンス、 
- IP+G, 
- OE5, 
- O365 Advanced Compliance 
- EMS E5


## <a name="what-does-the-default-policy-do"></a>既定のポリシーは何をしますか?

既定の DLP ポリシーは、組織に内部および外部で共有されるクレジット カード番号を追跡します。 このポリシーは、テナントのすべてのユーザーに対して既定でオンになっています。 エンド ユーザーのポリシー ヒントは生成されませんが、Alert イベントを生成し、管理者 (ポリシーに追加) への重大度の低い電子メールもトリガーします。 管理者は、コンプライアンス センターにログインして、アクティビティを表示し、ポリシーの詳細を編集できます。

管理者は、コンプライアンス センターの [データ損失防止ポリシー] [ページ>](https://compliance.microsoft.com/compliancesettings) ポリシーを表示できます。


> [!div class="mx-imgBorder"]
> ![既定の Teams DLP ポリシー](../media/default-teams-dlp-policy.png)

## <a name="edit-or-delete-the-default-policy"></a>既定のポリシーを編集または削除する

パフォーマンス [を向上するために既定のポリシーを](create-test-tune-dlp-policy.md#tune-a-dlp-policy)編集したり、削除したりするには **、DLP コンプライアンス** 管理のアクセス許可を持つアカウントを使用します。 詳細については、「アクセス許可」 [を参照してください](create-test-tune-dlp-policy.md#permissions)。

