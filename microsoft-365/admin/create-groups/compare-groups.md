---
title: グループを比較する
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: Microsoft 365 グループでは、メンバーは会話用のグループ メールおよび共有ワークスペース、ファイル、カレンダー イベント、ストリーム、Planner を利用できます。
ms.openlocfilehash: 12da954beb4d019b7652ef4df2e18cb30ff542ed
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393261"
---
# <a name="compare-groups"></a><span data-ttu-id="1c9dd-103">グループを比較する</span><span class="sxs-lookup"><span data-stu-id="1c9dd-103">Compare groups</span></span>

<span data-ttu-id="1c9dd-104">Microsoft 365 管理センターの [ **グループ**] セクションでは、次の種類のグループを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-104">In the **Groups** section of the Microsoft 365 admin center, you can create and manage these types of groups:</span></span> 

- <span data-ttu-id="1c9dd-105">**Microsoft 365 グループ** (旧称 Office 365 グループ) は、会社の内外のユーザー間での共同作業に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-105">**Microsoft 365 groups** (formerly Office 365 groups) are used for collaboration between users, both inside and outside your company.</span></span>
- <span data-ttu-id="1c9dd-106">**配布グループ** は、ユーザーのグループにメール通知を送信するのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-106">**Distribution groups** are used for sending email notifications to a group of people.</span></span>
- <span data-ttu-id="1c9dd-107">**セキュリティ グループ** は、SharePoint サイトなどのリソースへのアクセスを許可するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-107">**Security groups** are used for granting access to resources such as SharePoint sites.</span></span>
- <span data-ttu-id="1c9dd-108">**メールが有効なセキュリティ グループ** は、SharePoint などのリソースへのアクセスを許可し、それらのユーザーにメールで通知を送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-108">**Mail-enabled security groups** are used for granting access to resources such as SharePoint, and emailing notifications to those users.</span></span>
- <span data-ttu-id="1c9dd-109">**共有メールボックス** は、会社情報やサポート メール アドレスなど、複数のユーザーが同じメールボックスにアクセスする必要がある場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-109">**Shared mailboxes** are used when multiple people need access to the same mailbox, such as a company information or support email address.</span></span>

## <a name="microsoft-365-groups"></a><span data-ttu-id="1c9dd-110">Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="1c9dd-110">Microsoft 365 groups</span></span>

<span data-ttu-id="1c9dd-111">Microsoft 365 グループは、社内外のユーザー間での共同作業に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-111">Microsoft 365 groups are used for collaboration between users, both inside and outside your company.</span></span> <span data-ttu-id="1c9dd-112">各 Microsoft 365 グループでは、メンバーは会話用のグループ メールおよび共有ワークスペース、ファイル、カレンダー イベント、ストリーム、Planner を利用できます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-112">With each Microsoft 365 group, members get a group email and shared workspace for conversations, files, and calendar events, Stream and a Planner.</span></span>

<span data-ttu-id="1c9dd-113">[管理者によって有効にされている](manage-guest-access-in-groups.md)限り、組織の外部のユーザーをグループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-113">You can add people from outside your organization to a group as long as this has been [enabled by the administrator](manage-guest-access-in-groups.md).</span></span> <span data-ttu-id="1c9dd-114">外部の送信者がグループのメール アドレスにメールを送信できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-114">You can also allow external senders to send email to the group email address.</span></span>

<span data-ttu-id="1c9dd-115">Microsoft 365 グループは [Azure Active Directory の動的メンバーシップ用に構成でき](/azure/active-directory/users-groups-roles/groups-change-type)、部署、場所、役職などのユーザー属性に基づいてグループ メンバーを自動的に追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-115">Microsoft 365 groups can be [configured for dynamic membership in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type), allowing group members to be added or removed automatically based on user attributes such as department, location, title, etc.</span></span>

<span data-ttu-id="1c9dd-116">Microsoft 365 グループには、Outlook for iOS や Outlook for Android などのモバイル アプリからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-116">Microsoft 365 groups can be accessed through mobile apps such as Outlook for iOS and Outlook for Android.</span></span>

<span data-ttu-id="1c9dd-117">グループ メンバーは、[管理者によって有効にされている](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)場合、グループのメール アドレスとして送信したり、グループのメール アドレスの代わりに送信したりできます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-117">Group members can send as or send on behalf of the group email address if this has been [enabled by the administrator](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md).</span></span>

<span data-ttu-id="1c9dd-118">Microsoft 365 グループは、他の Microsoft 365 グループ、または配布グループやセキュリティ グループとのネストをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-118">Microsoft 365 groups don't support nesting with other Microsoft 365 groups or with distribution or security groups.</span></span>

## <a name="distribution-groups"></a><span data-ttu-id="1c9dd-119">配布グループ</span><span class="sxs-lookup"><span data-stu-id="1c9dd-119">Distribution groups</span></span>

<span data-ttu-id="1c9dd-120">[配布グループ](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)は、ユーザーのグループに通知を送信するのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-120">[Distribution groups](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) are used for sending notifications to a group of people.</span></span> <span data-ttu-id="1c9dd-121">管理者によって有効にされている場合、外部メールを受信できます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-121">They can receive external email if enabled by the administrator.</span></span>

<span data-ttu-id="1c9dd-122">配布グループは、"建物 A のユーザー" や "Contoso の全員" など、一連のユーザーに情報をブロードキャストする必要がある状況に最適です。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-122">Distribution groups are best for situations where you need to broadcast information to a set group of people, such as "People in Building A" or "Everyone at Contoso."</span></span>

<span data-ttu-id="1c9dd-123">配布グループは、[Microsoft 365 グループ](../manage/upgrade-distribution-lists.md)にアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-123">Distribution groups can be [upgraded to Microsoft 365 groups](../manage/upgrade-distribution-lists.md).</span></span>

<span data-ttu-id="1c9dd-124">配布グループは、Microsoft Teams のチームに追加できます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-124">Distribution groups can be added to a team in Microsoft Teams.</span></span>

<span data-ttu-id="1c9dd-125">Microsoft 365 グループは、配布グループのメンバーにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-125">Microsoft 365 groups can't be members of distribution groups.</span></span>

## <a name="security-groups"></a><span data-ttu-id="1c9dd-126">セキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="1c9dd-126">Security groups</span></span>

<span data-ttu-id="1c9dd-127">[セキュリティ グループ](../email/create-edit-or-delete-a-security-group.md)は、SharePoint などの Microsoft 365 リソースへのアクセスを許可するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-127">[Security groups](../email/create-edit-or-delete-a-security-group.md) are used for granting access to Microsoft 365 resources, such as SharePoint.</span></span> <span data-ttu-id="1c9dd-128">ユーザーを各リソースに個別に追加するのではなく、グループを管理するだけで済むため、管理が容易になります。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-128">They can make administration easier because you need only administer the group rather than adding users to each resource individually.</span></span>

<span data-ttu-id="1c9dd-p105">セキュリティ グループには、ユーザーまたはデバイスを含めることができます。デバイス用のセキュリティ グループの作成は、Intune などのモバイル デバイス管理サービスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-p105">Security groups can contain users or devices. Creating a security group for devices can be used with mobile device management services, such as Intune.</span></span>

<span data-ttu-id="1c9dd-131">セキュリティ グループは [Azure Active Directory の動的メンバーシップ用に構成でき](/azure/active-directory/users-groups-roles/groups-change-type)、部署、場所、役職などのユーザー属性、またはオペレーティング システムのバージョンなどのデバイス属性に基づいてグループ メンバーまたはデバイスを自動的に追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-131">Security groups can be [configured for dynamic membership in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type), allowing group members or devices to be added or removed automatically based on user attributes such as department, location, or title; or device attributes such as operating system version.</span></span>

<span data-ttu-id="1c9dd-132">セキュリティ グループをチームに追加できます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-132">Security groups can be added to a team.</span></span>

<span data-ttu-id="1c9dd-133">Microsoft 365 グループは、セキュリティ グループのメンバーにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-133">Microsoft 365 groups can't be members of security groups.</span></span>

## <a name="mail-enabled-security-groups"></a><span data-ttu-id="1c9dd-134">メールが有効なセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="1c9dd-134">Mail-enabled security groups</span></span>

<span data-ttu-id="1c9dd-135">メールが有効なセキュリティ グループは通常のセキュリティ グループと同じように機能しますが、Azure Active Directory で動的に管理できず、デバイスを含めることができません。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-135">Mail-enabled security groups function the same as regular security groups, except that they cannot be dynamically managed through Azure Active Directory and cannot contain devices.</span></span>

<span data-ttu-id="1c9dd-136">グループのすべてのメンバーにメールを送信する機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-136">They include the ability to send mail to all the members of the group.</span></span>

<span data-ttu-id="1c9dd-137">メール対応のセキュリティ グループをチームに追加できます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-137">Mail-enabled security groups can be added to a team.</span></span>

## <a name="shared-mailboxes"></a><span data-ttu-id="1c9dd-138">共有メールボックス</span><span class="sxs-lookup"><span data-stu-id="1c9dd-138">Shared mailboxes</span></span>

<span data-ttu-id="1c9dd-139">[共有メールボックス](../email/create-a-shared-mailbox.md)は、会社情報やサポート メール アドレス、受付デスク、または複数のユーザーが共有する可能性のあるその他の機能など、複数のユーザーが同じメールボックスにアクセスする必要がある場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-139">[Shared mailboxes](../email/create-a-shared-mailbox.md) are used when multiple people need access to the same mailbox, such as a company information or support email address, reception desk, or other function that might be shared by multiple people.</span></span>

<span data-ttu-id="1c9dd-140">管理者が有効にしている場合、共有メールボックスは外部メールを受信できます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-140">Shared mailboxes can receive external emails if the administrator has enabled this.</span></span>

<span data-ttu-id="1c9dd-141">共有メールボックスには、コラボレーションに使用できる予定表が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-141">Shared mailboxes include a calendar that can be used for collaboration.</span></span>

<span data-ttu-id="1c9dd-142">グループ メールボックスへのアクセス許可を持つユーザーは、管理者がそのユーザーに対して必要なアクセス許可を付与している場合、メールボックスのメール アドレスとして送信したり、メールボックスのメール アドレスの代わりに送信したりできます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-142">Users with permissions to the group mailbox can send as or send on behalf of the mailbox email address if the administrator has given that user permissions to do that.</span></span> <span data-ttu-id="1c9dd-143">これは、ユーザーが "Contoso サポート" や "建物 A の受付デスク" からメールを送信できるため、ヘルプとサポートのメールボックスとして特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-143">This is particularly useful for help and support mailboxes because users can send emails from "Contoso Support" or "Building A Reception Desk."</span></span>

<span data-ttu-id="1c9dd-144">現在、共有メールボックスを Microsoft 365 グループに移行することはできません。</span><span class="sxs-lookup"><span data-stu-id="1c9dd-144">It's not possible to migrate a shared mailbox to a Microsoft 365 group.</span></span> 

## <a name="related-content"></a><span data-ttu-id="1c9dd-145">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="1c9dd-145">Related content</span></span>

[<span data-ttu-id="1c9dd-146">Microsoft 365 グループについて</span><span class="sxs-lookup"><span data-stu-id="1c9dd-146">Learn about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="1c9dd-147">Outlook で配布リストを Microsoft 365 グループにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="1c9dd-147">Upgrade distribution lists to Microsoft 365 Groups in Outlook</span></span>](/microsoft-365/admin/manage/upgrade-distribution-lists)

[<span data-ttu-id="1c9dd-148">Outlook で配布リストをグループにアップグレードする理由</span><span class="sxs-lookup"><span data-stu-id="1c9dd-148">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)
