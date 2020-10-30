---
title: Outlook on the web で "アカウントが無効です" というエラーが表示される場合
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: ライセンスを付与されていないユーザーにライセンスを追加して、アカウント無効エラーを修正する方法について説明します。
ms.openlocfilehash: b05b19ceb3c4b173164d37f780fd558bdd2d8040
ms.sourcegitcommit: d578b28ed1886abd083b01b93f01b354067e6d47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "48804869"
---
# <a name="getting-an-account-disabled-error-in-outlook-on-the-web"></a>Outlook on the web でアカウントが無効になっているエラーを取得する

Web 上の Outlook (旧称 Outlook Web App) を開こうとしたときに、 **アカウントが無効になっ** ているというエラーが表示される場合は、 `X-OWA-Error: Microsoft.Exchange.Data.Storage.AccountDisabledException` 管理者が Web 上の outlook へのアクセスを無効にしている可能性があります。

管理者は、「 [メールボックスの Outlook Web App を有効または無効](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)にする」の手順に従って、このエラーを修正することができます。
