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
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft Cloud ドイツ Exchange Online からグローバル Exchange Online サービスに移行する方法について説明します。
ms.openlocfilehash: 41628b3032f5b268d5e32501b393fef31663dfc3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399232"
---
# <a name="update-your-mx-records-to-transition-to-the-global-exchange-online-service"></a><span data-ttu-id="5d6d4-103">グローバルな Exchange Online サービスに移行するように MX レコードを更新する</span><span class="sxs-lookup"><span data-stu-id="5d6d4-103">Update your MX records to transition to the global Exchange Online service</span></span>

1. <span data-ttu-id="5d6d4-104">[Microsoft 365 管理ポータル](https://admin.microsoft.com)にサインインし、[**設定**] [  >  **ドメイン**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="5d6d4-104">Sign in to [Microsoft 365 admin portal](https://admin.microsoft.com), and go to **Settings** > **Domains**</span></span>

2. <span data-ttu-id="5d6d4-105">状態は各ドメインの右側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d6d4-105">Status will be shown on the right side for each domain.</span></span> <span data-ttu-id="5d6d4-106">組織のドメインが Microsoft Cloud ドイツ Exchange Online を指している場合は、MX レコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d6d4-106">If your organization’s domains point to Microsoft Cloud Germany Exchange Online, you'll need to update your MX record.</span></span>

3. <span data-ttu-id="5d6d4-107">ドメインをクリックし、[**検出された DNS エラー] をクリックします。表示するには、ここをクリック**します。</span><span class="sxs-lookup"><span data-stu-id="5d6d4-107">Click the domain, then click **DNS errors detected, click here to view**.</span></span>

4. <span data-ttu-id="5d6d4-108">このページには、MX レコードを修正する方法を示す手順があります。</span><span class="sxs-lookup"><span data-stu-id="5d6d4-108">This page will have instructions to show you how to fix the MX record.</span></span> <span data-ttu-id="5d6d4-109">ドメインのレジストラーが[ドメイン接続](../setup/add-domain.md#registrars-with-domain-connect)を使用している場合は、上の [自分のレコードを修正] をクリックできます。</span><span class="sxs-lookup"><span data-stu-id="5d6d4-109">If your domain’s registrar uses [Domain Connect](../setup/add-domain.md#registrars-with-domain-connect), you can click “Fix my records” on top.</span></span> <span data-ttu-id="5d6d4-110">それ以外の場合は、ウィザードのリンクを使用して**レジストラーの詳しい**手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="5d6d4-110">Otherwise you can follow the link in the wizard to **step-by-step instructions** for your registrar.</span></span>