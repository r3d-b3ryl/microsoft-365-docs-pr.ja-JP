---
title: Microsoft Teams の既定のデータ損失防止ポリシーについて学ぶ (プレビュー)
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
description: このページの既定のデータ損失防止ポリシーについてMicrosoft Teams
ms.openlocfilehash: 8f021031bd1dc3672a7aa7123ce01d4c6536fe77
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58567738"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a>Microsoft Teams の既定のデータ損失防止ポリシーについて学ぶ (プレビュー)

[データ損失防止機能](dlp-learn-about-dlp.md)は、プライベート チャネル メッセージを含むMicrosoft Teamsチャネル メッセージを含む拡張されました。 このリリースの一環として、コンプライアンス センターに初めてお客様向Microsoft Teams DLP ポリシーを作成しました。

## <a name="applies-to"></a>適用対象

以下の 1 つ以上のライセンスでライセンスを取得し、アクティブなユーザーを持Teamsテナント
 
- ME5, 
- MA5, 
- E5/A5 コンプライアンス、 
- IP+G, 
- OE5, 
- O365 Advanced Compliance 
- EMS E5


## <a name="what-does-the-default-policy-do"></a>既定のポリシーは何をしますか?

既定の DLP ポリシーは、Teams外部で共有されているクレジット カード番号を追跡します。 このポリシーは、テナントのすべてのユーザーに対して既定でオンになっています。 エンド ユーザーのポリシー ヒントは生成されませんが、Alert イベントを生成し、管理者 (ポリシーに追加) への重大度の低い電子メールもトリガーします。 管理者は、コンプライアンス センターにログインして、アクティビティを表示し、ポリシーの詳細を編集できます。

管理者は、コンプライアンス センターの [データ損失防止ポリシー] [ページ>](https://compliance.microsoft.com/compliancesettings) ポリシーを表示できます。


> [!div class="mx-imgBorder"]
> ![DLP ポリシー Teams既定の値を使用します。](../media/default-teams-dlp-policy.png)

## <a name="edit-or-delete-the-default-policy"></a>既定のポリシーを編集または削除する

パフォーマンス [を向上するために既定のポリシーを](create-test-tune-dlp-policy.md#tune-a-dlp-policy)編集したり、削除したりするには **、DLP コンプライアンス** 管理のアクセス許可を持つアカウントを使用します。 詳細については、「アクセス許可」 [を参照してください](create-test-tune-dlp-policy.md#permissions)。

