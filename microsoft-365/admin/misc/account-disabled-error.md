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
# <a name="getting-an-account-disabled-error-in-outlook-on-the-web"></a><span data-ttu-id="94dda-103">Outlook on the web でアカウントが無効になっているエラーを取得する</span><span class="sxs-lookup"><span data-stu-id="94dda-103">Getting an account disabled error in Outlook on the web</span></span>

<span data-ttu-id="94dda-104">Web 上の Outlook (旧称 Outlook Web App) を開こうとしたときに、 **アカウントが無効になっ** ているというエラーが表示される場合は、 `X-OWA-Error: Microsoft.Exchange.Data.Storage.AccountDisabledException` 管理者が Web 上の outlook へのアクセスを無効にしている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="94dda-104">If you get the error **Your account has been disabled** with `X-OWA-Error: Microsoft.Exchange.Data.Storage.AccountDisabledException` when you try to open Outlook on the web (formerly known as Outlook Web App), your admin might have disabled your access to Outlook on the web.</span></span>

<span data-ttu-id="94dda-105">管理者は、「 [メールボックスの Outlook Web App を有効または無効](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)にする」の手順に従って、このエラーを修正することができます。</span><span class="sxs-lookup"><span data-stu-id="94dda-105">Your admin can fix this error by following the steps in the topic [Enable or disable Outlook Web App for a mailbox](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app).</span></span>
