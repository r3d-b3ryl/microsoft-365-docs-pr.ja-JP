---
title: スタンドアロン EOP で受信者を管理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 2921f544-8257-4bae-8e3a-ce9250e9f162
ms.custom:
- seo-marvel-apr2020
description: 管理者は、スタンドアロンの Exchange Online Protection (EOP) でさまざまな種類の受信者オブジェクトについて学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 20d1c3e77c916e2c04a9c35eceb410859eb85ba0
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150269"
---
# <a name="manage-recipients-in-standalone-eop"></a><span data-ttu-id="1cd64-103">スタンドアロン EOP で受信者を管理する</span><span class="sxs-lookup"><span data-stu-id="1cd64-103">Manage recipients in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1cd64-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="1cd64-104">**Applies to**</span></span>
-  [<span data-ttu-id="1cd64-105">Exchange Online Protection スタンドアロン</span><span class="sxs-lookup"><span data-stu-id="1cd64-105">Exchange Online Protection standalone</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)

<span data-ttu-id="1cd64-106">Exchange Online メールボックスのないスタンドアロン Exchange Online Protection (EOP) 組織は、次の種類の受信者をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1cd64-106">Standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support the following types of recipients:</span></span>

- <span data-ttu-id="1cd64-107">**メール ユーザー**: メール ユーザーは、スタンドアロン EOP 組織の基本的な種類のユーザー アカウントです。</span><span class="sxs-lookup"><span data-stu-id="1cd64-107">**Mail users**: Mail users are the fundamental type of user accounts in your standalone EOP organization.</span></span> <span data-ttu-id="1cd64-108">メール ユーザーは EOP 組織内のログオン資格情報を持っていますが、外部の電子メール アドレスを持っています (メール ユーザーのメールボックスは EOP 組織の外部に保存されています)。</span><span class="sxs-lookup"><span data-stu-id="1cd64-108">Mail users have logon credentials in your EOP organization, but they have external email addresses (their mailboxes are located outside of your EOP organization).</span></span>

  <span data-ttu-id="1cd64-109">EOP でのメール ユーザーの管理方法については、「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cd64-109">For more information about managing mail users in EOP, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

- <span data-ttu-id="1cd64-110">**グループ**: 次の種類のグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1cd64-110">**Groups**: You can create the following types of groups:</span></span>

  - <span data-ttu-id="1cd64-111">配布グループ</span><span class="sxs-lookup"><span data-stu-id="1cd64-111">Distribution groups</span></span>
  - <span data-ttu-id="1cd64-112">メールが有効なセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="1cd64-112">Mail-enabled security groups</span></span>

  <span data-ttu-id="1cd64-113">EOP でのグループの管理方法については、「[EOP でグループを管理する](manage-groups-in-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cd64-113">For more information about managing groups in EOP, see [Manage groups in EOP](manage-groups-in-eop.md).</span></span>
