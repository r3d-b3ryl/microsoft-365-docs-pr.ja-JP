---
title: Exchange Online 管理者の役割について
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 097ae285-c4af-4319-9770-e2559d66e4c8
description: 'Exchange Online 管理者は、組織の電子メールとメールボックスを管理します。 たとえば、ユーザーのメールボックス内の削除済みアイテムを回復します。 '
ms.openlocfilehash: 5b63f2b0a58fdce75e5d70e329b8a0d02fb94a1a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51050972"
---
# <a name="about-the-exchange-online-admin-role"></a><span data-ttu-id="312b3-104">Exchange Online 管理者の役割について</span><span class="sxs-lookup"><span data-stu-id="312b3-104">About the Exchange Online admin role</span></span>

<span data-ttu-id="312b3-105">Microsoft 365 の管理を支援するために[](assign-admin-roles.md)、Exchange 管理センターから組織のメールとメールボックスを管理するためのアクセス許可をユーザーに割[り当てできます](/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="312b3-105">To help you administer Microsoft 365, you can [assign](assign-admin-roles.md) users permissions to manage your organization's email and mailboxes from the [Exchange admin center](/exchange/exchange-admin-center).</span></span> <span data-ttu-id="312b3-106">それには、対象のユーザーを Exchange 管理者の役割に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="312b3-106">You do this by assigning them to the Exchange admin role.</span></span>
  
 <span data-ttu-id="312b3-107">**ヒント**:ユーザーを Exchange 管理者の役割に割り当てる場合は、そのユーザーをサービス管理者の役割にも割り当てます。</span><span class="sxs-lookup"><span data-stu-id="312b3-107">**Tip**: When you assign someone to the Exchange admin role, also assign them to the Service admin role.</span></span> <span data-ttu-id="312b3-108">これにより、Exchange Online サービスの正常性、変更およびリリース通知など、Microsoft 365 管理センターで重要な情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="312b3-108">This way they can see important information in the Microsoft 365 admin center, such as the health of the Exchange Online service, and change and release notifications.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="312b3-109">はじめに</span><span class="sxs-lookup"><span data-stu-id="312b3-109">Before you begin</span></span>

<span data-ttu-id="312b3-110">Exchange 管理者の役割を割り当てられた場合にユーザーが実行できる重要なタスクのいくつかを次に説明します。</span><span class="sxs-lookup"><span data-stu-id="312b3-110">Here are some of the key tasks users can do when they are assigned to the Exchange admin role:</span></span>
  
- [<span data-ttu-id="312b3-111">ユーザーのメールボックスで削除されたアイテムを復元する</span><span class="sxs-lookup"><span data-stu-id="312b3-111">Recover deleted items in a user mailbox - Admin Help</span></span>](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- <span data-ttu-id="312b3-112">[組織内のメールボックスのアーカイブポリシーと削除ポリシーを設定します](../../compliance/set-up-an-archive-and-deletion-policy-for-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="312b3-112">[Set up an archive and deletion policy for mailboxes in your organization](../../compliance/set-up-an-archive-and-deletion-policy-for-mailboxes.md).</span></span>

- <span data-ttu-id="312b3-113">メールボックスの機能をセットアップします。たとえば、メールボックス共有ポリシーを設定すると、ユーザーが予定表や連絡先の情報を組織外の人とどのように共有できるかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="312b3-113">Set up mailbox features such as the mailbox sharing policy: how users can share calendar and contacts information with others outside of your organization.</span></span>

- <span data-ttu-id="312b3-114">"Send[as](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" と "[Send onhalf](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)" delegates for someone's mailbox.</span><span class="sxs-lookup"><span data-stu-id="312b3-114">Set up "[Send as](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" and "[Send on behalf](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)" delegates for someone's mailbox.</span></span> <span data-ttu-id="312b3-115">たとえば、経営幹部は、メールの送信を代理でアシスタントに行ってもらう場合があります。</span><span class="sxs-lookup"><span data-stu-id="312b3-115">For example, an executive may want their assistant to have the ability to send mail on their behalf.</span></span>

- <span data-ttu-id="312b3-116">[共有メールボックスを作成して](../email/create-a-shared-mailbox.md) 、ユーザーのグループが共通のメール アドレスからメールを監視および送信できます。</span><span class="sxs-lookup"><span data-stu-id="312b3-116">[Create a shared mailbox](../email/create-a-shared-mailbox.md) so a group of people can monitor and send email from a common email address.</span></span>

- <span data-ttu-id="312b3-117">[組織のスパム対策と](https://docs.microsoft.com/microsoft-365/security/defender-365-security/anti-spam-protection) マルウェア フィルターを電子メールで送信します。</span><span class="sxs-lookup"><span data-stu-id="312b3-117">[Email anti-spam protection](https://docs.microsoft.com/microsoft-365/security/defender-365-security/anti-spam-protection) and malware filters for the organization.</span></span>

- <span data-ttu-id="312b3-118">Microsoft 365 グループを管理する</span><span class="sxs-lookup"><span data-stu-id="312b3-118">Manage Microsoft 365 groups</span></span>

## <a name="exchange-online-role-groups"></a><span data-ttu-id="312b3-119">Exchange Online の役割グループ</span><span class="sxs-lookup"><span data-stu-id="312b3-119">Exchange Online role groups</span></span>

<span data-ttu-id="312b3-p105">大規模な組織では、Exchange 管理者がユーザーを Exchange の役割グループに割り当てることがあります。役割グループに追加されたユーザーは、そのグループのメンバーだけに許可されている、特定のビジネス機能を実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="312b3-p105">If you have a large organization, the Exchange admin might want to assign users to Exchange role groups. When an admin adds a user to a role group, the user gets permissions to perform certain business functions only members of that group can do.</span></span>
  
 <span data-ttu-id="312b3-p106">たとえば、証拠開示管理という役割グループに割り当てられたユーザーは、メールボックスの検索を実行して条件に一致するデータを得ることができます。詳細については、「 [Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」と「[役割グループの管理](/exchange/manage-role-groups-exchange-2013-help)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="312b3-p106">For example, the Exchange admin might assign someone to the Discovery Management role group so they can perform searches of mailboxes for data that meets certain criteria. To learn more, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Manage Role Groups](/exchange/manage-role-groups-exchange-2013-help).</span></span>
  
## <a name="learn-about-other-admin-roles"></a><span data-ttu-id="312b3-124">他の管理者ロールの詳細</span><span class="sxs-lookup"><span data-stu-id="312b3-124">Learn about other admin roles</span></span>

- [<span data-ttu-id="312b3-125">Microsoft 365 管理者ロールについて</span><span class="sxs-lookup"><span data-stu-id="312b3-125">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

- [<span data-ttu-id="312b3-126">SharePoint Online 管理者の役割について</span><span class="sxs-lookup"><span data-stu-id="312b3-126">About the SharePoint Online admin role</span></span>](/sharepoint/sharepoint-admin-role)

- [<span data-ttu-id="312b3-127">Skype for Business 管理者の役割について</span><span class="sxs-lookup"><span data-stu-id="312b3-127">About the Skype for Business admin role</span></span>](/skypeforbusiness/skype-for-business-online)

- [<span data-ttu-id="312b3-128">Microsoft Teams 管理者の役割を使用する</span><span class="sxs-lookup"><span data-stu-id="312b3-128">Use Microsoft Teams admin role</span></span>](/MicrosoftTeams/using-admin-roles)