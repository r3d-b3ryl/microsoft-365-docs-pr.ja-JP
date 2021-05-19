---
title: Outlook on the web で「メールボックスが見つかりませんでした」というエラーが表示される場合
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: 「**のメールボックス見つかりませんでした**」 というエラーは、Outlook on the web への接続に使用したアカウントに Exchange Online のライセンスが存在しないという意味です。
ms.openlocfilehash: 5ae850da3b9a4022c01f8bf4469f5e86f44b10bd
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537441"
---
# <a name="getting-a-mailbox-not-found-error-in-outlook-on-the-web"></a>Outlook on the web で「メールボックスが見つかりませんでした」というエラーが表示されますか?

Outlook on the web を使用しているときに、「**メールボックスが見つかりませんでした**」というエラーが表示された場合は、Outlook on the web への接続時に使用したアカウントに Exchange Online ライセンスが付与されていないため、そのアカウントにメールボックスが関連付けられていません。 

## <a name="assign-a-license-to-your-account"></a>アカウントにライセンスを割り当てる

管理者は、次の手順に従って、アカウントにライセンスを割り当てることができます。

1. [Microsoft 365 管理センター](https://portal.office.com/adminportal/home#/homepage)を開き、[**ユーザー**] セクションの [**アクティブ ユーザー**] に移動して、エラーが表示されているユーザーを選択します。
1. 開いたユーザー ページで、[**ライセンスとアプリ**] セクションに移動し、該当する [**場所**] の値を選択し、Exchange Online を含むライセンスを割り当てます (ライセンスを展開して、その詳細を表示します)。 
1. 完了したら、[**変更の保存**] をクリックします。

## <a name="related-content"></a>関連コンテンツ

[ユーザーに別のメール エイリアスを追加する](../email/add-another-email-alias-for-a-user.md) (記事)

[Microsoft 365 でメールの転送を構成する](../email/configure-email-forwarding.md) (記事)

[共有メールボックス GWT を作成する](../email/create-a-shared-mailbox.md) (記事)