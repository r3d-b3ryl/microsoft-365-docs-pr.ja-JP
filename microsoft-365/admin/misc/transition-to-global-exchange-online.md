---
title: グローバルな Exchange Online サービスに移行するように MX レコードを更新する
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft Cloud ドイツ Exchange Online からグローバル Exchange Online サービスに移行する方法について説明します。
ms.openlocfilehash: 276a12095cbad5b9bcaf1c48fe5d26ee20232e54
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "44003022"
---
# <a name="update-your-mx-records-to-transition-to-the-global-exchange-online-service"></a><span data-ttu-id="70912-103">グローバルな Exchange Online サービスに移行するように MX レコードを更新する</span><span class="sxs-lookup"><span data-stu-id="70912-103">Update your MX records to transition to the global Exchange Online service</span></span>

1. <span data-ttu-id="70912-104">[Microsoft 365 管理ポータル](https://admin.microsoft.com)にサインインし、[**設定** > ] [**ドメイン**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="70912-104">Sign in to [Microsoft 365 admin portal](https://admin.microsoft.com), and go to **Settings** > **Domains**</span></span>

2. <span data-ttu-id="70912-105">状態は各ドメインの右側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="70912-105">Status will be shown on the right side for each domain.</span></span> <span data-ttu-id="70912-106">組織のドメインが Microsoft Cloud ドイツ Exchange Online を指している場合は、MX レコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70912-106">If your organization’s domains point to Microsoft Cloud Germany Exchange Online, you'll need to update your MX record.</span></span>

3. <span data-ttu-id="70912-107">ドメインをクリックし、[**検出された DNS エラー] をクリックします。表示するには、ここをクリック**します。</span><span class="sxs-lookup"><span data-stu-id="70912-107">Click the domain, then click **DNS errors detected, click here to view**.</span></span>

4. <span data-ttu-id="70912-108">このページには、MX レコードを修正する方法を示す手順があります。</span><span class="sxs-lookup"><span data-stu-id="70912-108">This page will have instructions to show you how to fix the MX record.</span></span> <span data-ttu-id="70912-109">ドメインのレジストラーが[ドメイン接続](../setup/add-domain.md#registrars-with-domain-connect)を使用している場合は、上の [自分のレコードを修正] をクリックできます。</span><span class="sxs-lookup"><span data-stu-id="70912-109">If your domain’s registrar uses [Domain Connect](../setup/add-domain.md#registrars-with-domain-connect), you can click “Fix my records” on top.</span></span> <span data-ttu-id="70912-110">それ以外の場合は、ウィザードのリンクを使用して**レジストラーの詳しい**手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="70912-110">Otherwise you can follow the link in the wizard to **step-by-step instructions** for your registrar.</span></span>