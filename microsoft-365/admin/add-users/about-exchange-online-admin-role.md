---
title: Exchange Online 管理者の役割について
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
description: 'Exchange online 管理者は、組織のメールとメールボックスを管理します。 たとえば、ユーザーのメールボックス内の削除済みのアイテムを復元します。 '
ms.openlocfilehash: cf7bd2a7856017ccf4f17f71ad1845b56b004a10
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387427"
---
# <a name="about-the-exchange-online-admin-role"></a><span data-ttu-id="d53de-104">Exchange Online 管理者の役割について</span><span class="sxs-lookup"><span data-stu-id="d53de-104">About the Exchange Online admin role</span></span>

<span data-ttu-id="d53de-105">Microsoft 365 を管理するために、 [Exchange 管理センター](https://go.microsoft.com/fwlink/p/?LinkID=271807)から組織の電子メールとメールボックスを管理するためのアクセス許可をユーザーに[割り当てる](assign-admin-roles.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="d53de-105">To help you administer Microsoft 365, you can [assign](assign-admin-roles.md) users permissions to manage your organization's email and mailboxes from the [Exchange admin center](https://go.microsoft.com/fwlink/p/?LinkID=271807).</span></span> <span data-ttu-id="d53de-106">それには、対象のユーザーを Exchange 管理者の役割に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d53de-106">You do this by assigning them to the Exchange admin role.</span></span> 
  
 <span data-ttu-id="d53de-107">**ヒント**:ユーザーを Exchange 管理者の役割に割り当てる場合は、そのユーザーをサービス管理者の役割にも割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d53de-107">**Tip**: When you assign someone to the Exchange admin role, also assign them to the Service admin role.</span></span> <span data-ttu-id="d53de-108">これにより、Exchange Online サービスの正常性、変更通知、リリース通知など、Microsoft 365 管理センターでの重要な情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d53de-108">This way they can see important information in the Microsoft 365 admin center, such as the health of the Exchange Online service, and change and release notifications.</span></span> 
  
<span data-ttu-id="d53de-109">Exchange 管理者の役割を割り当てられた場合にユーザーが実行できる重要なタスクのいくつかを次に説明します。</span><span class="sxs-lookup"><span data-stu-id="d53de-109">Here are some of the key tasks users can do when they are assigned to the Exchange admin role:</span></span> 
  
- [<span data-ttu-id="d53de-110">ユーザーのメールボックスで削除されたアイテムを復元する</span><span class="sxs-lookup"><span data-stu-id="d53de-110">Recover deleted items in a user mailbox - Admin Help</span></span>](https://docs.microsoft.com/office365/enterprise/recover-deleted-items-in-a-mailbox)
    
- <span data-ttu-id="d53de-111">[組織内のメールボックスのアーカイブと削除のポリシーを設定](https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes)します。</span><span class="sxs-lookup"><span data-stu-id="d53de-111">[Set up an archive and deletion policy for mailboxes in your organization](https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes).</span></span>
    
- <span data-ttu-id="d53de-112">メールボックスの機能をセットアップします。たとえば、メールボックス共有ポリシーを設定すると、ユーザーが予定表や連絡先の情報を組織外の人とどのように共有できるかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d53de-112">Set up mailbox features such as the mailbox sharing policy: how users can share calendar and contacts information with others outside of your organization.</span></span> 
    
- <span data-ttu-id="d53de-113">他のユーザーのメールボックスの [[送信者](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)] および [[送信 abehalf](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)] の代理人を設定します。</span><span class="sxs-lookup"><span data-stu-id="d53de-113">Set up "[Send as](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" and "[Send on abehalf](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)" delegates for someone's mailbox.</span></span> <span data-ttu-id="d53de-114">たとえば、経営幹部は、メールの送信を代理でアシスタントに行ってもらう場合があります。</span><span class="sxs-lookup"><span data-stu-id="d53de-114">For example, an executive may want their assistant to have the ability to send mail on their behalf.</span></span> 
    
- <span data-ttu-id="d53de-115">ユーザーのグループが共通の電子メールアドレスからメールを監視して送信できるように、[共有メールボックスを作成](../email/create-a-shared-mailbox.md)します。</span><span class="sxs-lookup"><span data-stu-id="d53de-115">[Create a shared mailbox](../email/create-a-shared-mailbox.md) so a group of people can monitor and send email from a common email address.</span></span> 
    
- <span data-ttu-id="d53de-116">組織の[電子メールのスパム対策保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection)とマルウェアフィルター。</span><span class="sxs-lookup"><span data-stu-id="d53de-116">[Email anti-spam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) and malware filters for the organization.</span></span> 
    
- <span data-ttu-id="d53de-117">Microsoft 365 グループを管理する</span><span class="sxs-lookup"><span data-stu-id="d53de-117">Manage Microsoft 365 groups</span></span>
    
## <a name="exchange-online-role-groups"></a><span data-ttu-id="d53de-118">Exchange Online の役割グループ</span><span class="sxs-lookup"><span data-stu-id="d53de-118">Exchange Online role groups</span></span>

<span data-ttu-id="d53de-p105">大規模な組織では、Exchange 管理者がユーザーを Exchange の役割グループに割り当てることがあります。役割グループに追加されたユーザーは、そのグループのメンバーだけに許可されている、特定のビジネス機能を実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d53de-p105">If you have a large organization, the Exchange admin might want to assign users to Exchange role groups. When an admin adds a user to a role group, the user gets permissions to perform certain business functions only members of that group can do.</span></span>
  
 <span data-ttu-id="d53de-p106">たとえば、証拠開示管理という役割グループに割り当てられたユーザーは、メールボックスの検索を実行して条件に一致するデータを得ることができます。詳細については、「 [Exchange Online のアクセス許可](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)」と「[役割グループの管理](https://docs.microsoft.com/exchange/manage-role-groups-exchange-2013-help)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d53de-p106">For example, the Exchange admin might assign someone to the Discovery Management role group so they can perform searches of mailboxes for data that meets certain criteria. To learn more, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) and [Manage Role Groups](https://docs.microsoft.com/exchange/manage-role-groups-exchange-2013-help).</span></span>
  
## <a name="learn-about-other-admin-roles"></a><span data-ttu-id="d53de-123">その他の管理者の役割について説明します。</span><span class="sxs-lookup"><span data-stu-id="d53de-123">Learn about other admin roles</span></span>
    
- [<span data-ttu-id="d53de-124">SharePoint Online 管理者の役割について</span><span class="sxs-lookup"><span data-stu-id="d53de-124">About the SharePoint Online admin role</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)
    
- [<span data-ttu-id="d53de-125">Skype for Business 管理者の役割について</span><span class="sxs-lookup"><span data-stu-id="d53de-125">About the Skype for Business admin role</span></span>](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online)
    
