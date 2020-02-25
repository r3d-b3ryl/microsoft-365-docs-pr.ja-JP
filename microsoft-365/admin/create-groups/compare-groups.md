---
title: Office 365 でのグループの比較
ms.reviewer: arvaradh
f1.keywords:
- CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: Office 365 で使用できるグループの種類について説明します。
ms.openlocfilehash: 5b8a3a7859a510a07b579f3b1da255e555d6ae1f
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241404"
---
# <a name="compare-groups"></a><span data-ttu-id="46e74-103">グループを比較する</span><span class="sxs-lookup"><span data-stu-id="46e74-103">Compare groups</span></span>

<span data-ttu-id="46e74-104">Microsoft 365 管理センターの [ **グループ**] セクションでは、次の種類のグループを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="46e74-104">In the **Groups** section of the Microsoft 365 admin center, you can create and manage these types of groups:</span></span> 

- <span data-ttu-id="46e74-105">**Office 365 グループ**は、社内外のユーザー間での共同作業に使用されます。</span><span class="sxs-lookup"><span data-stu-id="46e74-105">**Office 365 groups** are used for collaboration between users, both inside and outside your company.</span></span>
- <span data-ttu-id="46e74-106">**配布グループ**は、ユーザーのグループに通知を送信するのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="46e74-106">**Distribution groups** are used for sending notifications to a group of people.</span></span>
- <span data-ttu-id="46e74-107">**セキュリティ グループ**は、SharePoint リソースへのアクセスを許可するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="46e74-107">**Security groups** are used for granting access to SharePoint resources.</span></span>
- <span data-ttu-id="46e74-108">**メールが有効なセキュリティ グループ**は、SharePoint リソースへのアクセスを許可し、それらのユーザーにメールで通知を送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="46e74-108">**Mail-enabled security groups** are used for granting access to SharePoint resources, and emailing notifications to those users.</span></span>
- <span data-ttu-id="46e74-109">**共有メールボックス**は、会社情報やサポート メール アドレスなど、複数のユーザーが同じメールボックスにアクセスする必要がある場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="46e74-109">**Shared mailboxes** are used when multiple people need access to the same mailbox, such as a company information or support email address.</span></span>

## <a name="office-365-groups"></a><span data-ttu-id="46e74-110">Office 365 グループ</span><span class="sxs-lookup"><span data-stu-id="46e74-110">Office 365 groups</span></span>

<span data-ttu-id="46e74-111">Office 365 グループは、社内外のユーザー間での共同作業に使用されます。</span><span class="sxs-lookup"><span data-stu-id="46e74-111">Office 365 groups are used for collaboration between users, both inside and outside your company.</span></span> <span data-ttu-id="46e74-112">各 Office 365 グループでは、メンバーは会話、ファイル、カレンダー イベント、Planner 用のグループ メールおよび共有ワークスペースを取得します。</span><span class="sxs-lookup"><span data-stu-id="46e74-112">With each Office 365 group, members get a group email and shared workspace for conversations, files, and calendar events, and a Planner.</span></span>

<span data-ttu-id="46e74-113">[管理者によって有効にされている](manage-guest-access-in-groups.md)限り、会社の外部のユーザーをグループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="46e74-113">You can add users external to your company to a group as long as this has been [enabled by the administrator](manage-guest-access-in-groups.md).</span></span> <span data-ttu-id="46e74-114">外部の送信者がグループのメール アドレスにメールを送信できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="46e74-114">You can also allow external senders to send email to the group email address.</span></span>

<span data-ttu-id="46e74-115">Office 365 グループは [Azure Active Directory の動的メンバーシップ用に構成でき](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)、部署、場所、役職などのユーザー属性に基づいてグループ メンバーを自動的に追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="46e74-115">Office 365 groups can be [configured for dynamic membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type), allowing group members to be added or removed automatically based on user attributes such as department, location, title, etc.</span></span>

<span data-ttu-id="46e74-116">Office 365 グループには、Outlook for iOS や Outlook for Android などのモバイル アプリからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="46e74-116">Office 365 groups can be accessed through mobile apps such as Outlook for iOS and Outlook for Android.</span></span>

<span data-ttu-id="46e74-117">グループ メンバーは、[管理者によって有効にされている](allow-members-to-send-as-or-send-on-behalf-of-group.md)場合、グループのメール アドレスとして送信したり、グループのメール アドレスの代わりに送信したりできます。</span><span class="sxs-lookup"><span data-stu-id="46e74-117">Group members can send as or send on behalf of the group email address if this has been [enabled by the administrator](allow-members-to-send-as-or-send-on-behalf-of-group.md).</span></span>

## <a name="distribution-groups"></a><span data-ttu-id="46e74-118">配布グループ</span><span class="sxs-lookup"><span data-stu-id="46e74-118">Distribution groups</span></span>

<span data-ttu-id="46e74-119">[配布グループ](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)は、ユーザーのグループに通知を送信するのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="46e74-119">[Distribution groups](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) are used for sending notifications to a group of people.</span></span> <span data-ttu-id="46e74-120">管理者によって有効にされている場合、外部メールを受信できます。</span><span class="sxs-lookup"><span data-stu-id="46e74-120">They can receive external email if enabled by the administrator.</span></span>

<span data-ttu-id="46e74-121">配布グループは、"建物 A のユーザー" や "Contoso の全員" など、一連のユーザーに情報をブロードキャストする必要がある状況に最適です。</span><span class="sxs-lookup"><span data-stu-id="46e74-121">Distribution groups are best for situations where you need to broadcast information to a set group of people, such as "People in Building A" or "Everyone at Contoso."</span></span>

## <a name="security-groups"></a><span data-ttu-id="46e74-122">セキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="46e74-122">Security groups</span></span>

<span data-ttu-id="46e74-123">[セキュリティ グループ](../email/create-edit-or-delete-a-security-group.md)は、SharePoint などの Office 365 リソースへのアクセスを許可するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="46e74-123">[Security groups](../email/create-edit-or-delete-a-security-group.md) are used for granting access to Office 365 resources, such as SharePoint.</span></span> <span data-ttu-id="46e74-124">ユーザーを各リソースに個別に追加するのではなく、グループを管理するだけで済むため、管理が容易になります。</span><span class="sxs-lookup"><span data-stu-id="46e74-124">They can make administration easier because you need only administer the group rather than adding users to each resource individually.</span></span>

<span data-ttu-id="46e74-125">セキュリティ グループには、ユーザーまたはデバイスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="46e74-125">Security groups can contain users or devices.</span></span> <span data-ttu-id="46e74-126">デバイス用のセキュリティ グループの作成は、Intune などのモバイル デバイス管理サービスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="46e74-126">Creating a security group for devices can be used with mobile device management services, such as Intune.</span></span>

<span data-ttu-id="46e74-127">セキュリティ グループは [Azure Active Directory の動的メンバーシップ用に構成でき](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)、部署、場所、役職などのユーザー属性、またはオペレーティング システムのバージョンなどのデバイス属性に基づいてグループ メンバーまたはデバイスを自動的に追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="46e74-127">Security groups can be [configured for dynamic membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type), allowing group members or devices to be added or removed automatically based on user attributes such as department, location, or title; or device attributes such as operating system version.</span></span>

## <a name="mail-enabled-security-groups"></a><span data-ttu-id="46e74-128">メールが有効なセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="46e74-128">Mail-enabled security groups</span></span>

<span data-ttu-id="46e74-129">メールが有効なセキュリティ グループは通常のセキュリティ グループと同じように機能しますが、Azure Active Directory で動的に管理できず、デバイスを含めることができません。</span><span class="sxs-lookup"><span data-stu-id="46e74-129">Mail-enabled security groups function the same as regular security groups, except that they cannot be dynamically managed through Azure Active Directory and cannot contain devices.</span></span>

<span data-ttu-id="46e74-130">グループのすべてのメンバーにメールを送信する機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="46e74-130">They include the ability to send mail to all the members of the group.</span></span>

## <a name="shared-mailboxes"></a><span data-ttu-id="46e74-131">共有メールボックス</span><span class="sxs-lookup"><span data-stu-id="46e74-131">Shared mailboxes</span></span>

<span data-ttu-id="46e74-132">[共有メールボックス](../email/create-a-shared-mailbox.md)は、会社情報やサポート メール アドレス、受付デスク、または複数のユーザーが共有する可能性のあるその他の機能など、複数のユーザーが同じメールボックスにアクセスする必要がある場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="46e74-132">[Shared mailboxes](../email/create-a-shared-mailbox.md) are used when multiple people need access to the same mailbox, such as a company information or support email address, reception desk, or other function that might be shared by multiple people.</span></span>

<span data-ttu-id="46e74-133">管理者が有効にしている場合、共有メールボックスは外部メールを受信できます。</span><span class="sxs-lookup"><span data-stu-id="46e74-133">Shared mailboxes can receive external emails if the administrator has enabled this.</span></span>

<span data-ttu-id="46e74-134">グループ メールボックスへのアクセス許可を持つユーザーは、管理者がそのユーザーに対して必要なアクセス許可を付与している場合、メールボックスのメール アドレスとして送信したり、メールボックスのメール アドレスの代わりに送信したりできます。</span><span class="sxs-lookup"><span data-stu-id="46e74-134">Users with permissions to the group mailbox can send as or send on behalf of the mailbox email address if the administrator has given that user permissions to do that.</span></span> <span data-ttu-id="46e74-135">これは、ユーザーが "Contoso サポート" や "建物 A の受付デスク" からメールを送信できるため、ヘルプとサポートのメールボックスとして特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="46e74-135">This is particularly useful for help and support mailboxes because users can send emails from "Contoso Support" or "Building A Reception Desk."</span></span>

<span data-ttu-id="46e74-136">現在、共有メールボックスを Office 365 グループに移行することはできません。</span><span class="sxs-lookup"><span data-stu-id="46e74-136">Currently it's not possible to migrate a shared mailbox to an Office 365 Group.</span></span> <span data-ttu-id="46e74-137">これはあなたが必要とするものでしたか ?</span><span class="sxs-lookup"><span data-stu-id="46e74-137">Is this something you want?</span></span> <span data-ttu-id="46e74-138">ご意見やご要望をお待ちしております。</span><span class="sxs-lookup"><span data-stu-id="46e74-138">Let us know.</span></span> <span data-ttu-id="46e74-139">**[ここで投票してください。](https://go.microsoft.com/fwlink/?linkid=871518)**</span><span class="sxs-lookup"><span data-stu-id="46e74-139">**[Vote here](https://go.microsoft.com/fwlink/?linkid=871518)**</span></span>

## <a name="related-articles"></a><span data-ttu-id="46e74-140">関連記事</span><span class="sxs-lookup"><span data-stu-id="46e74-140">Related articles</span></span>

[<span data-ttu-id="46e74-141">Office 365 グループの詳細</span><span class="sxs-lookup"><span data-stu-id="46e74-141">Learn about Office 365 Groups</span></span>](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2)
