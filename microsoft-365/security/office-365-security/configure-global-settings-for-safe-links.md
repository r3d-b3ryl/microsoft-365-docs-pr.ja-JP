---
title: Defender for Office 365 のセーフ リンク設定のグローバル設定を構成する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、Microsoft Defender for Office 365 のセーフ リンクのグローバル設定 ([次の URL をブロックする] リストと Office 365 アプリの保護) を表示および構成する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e3466f515458b05a5c00053a30fad8f5a84802fd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906566"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="de217-103">365 用 Microsoft Defender のセーフ リンクのグローバルOffice構成する</span><span class="sxs-lookup"><span data-stu-id="de217-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="de217-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="de217-104">**Applies to**</span></span>
- [<span data-ttu-id="de217-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="de217-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="de217-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="de217-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> <span data-ttu-id="de217-107">この記事は、[Microsoft Defender for Office 365](office-365-atp.md) をご利用の法人のお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="de217-107">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="de217-108">Outlook で Safelinks に関する情報を探しているホーム ユーザーの場合は、「Advanced [Outlook.com セキュリティ」を参照してください](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="de217-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="de217-109">セーフ リンクは [、Microsoft Defender for Office 365](office-365-atp.md) の機能で、メール フロー内の受信電子メール メッセージの URL スキャンと、電子メール メッセージ内の URL とリンクのクリック検証の時間を提供します。</span><span class="sxs-lookup"><span data-stu-id="de217-109">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="de217-110">詳細については [、「Safe Links in Microsoft Defender for microsoft Defender for Office 365」を参照してください](atp-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="de217-110">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="de217-111">セーフ リンク ポリシーでは、ほとんどのセーフ リンク設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="de217-111">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="de217-112">手順については [、「Set up Safe Links policies in Microsoft Defender for Office 365」を参照してください](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="de217-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

<span data-ttu-id="de217-113">ただし、セーフ リンクは、アクティブなセーフ リンク ポリシーに含まれるすべてのユーザーに適用されるグローバル設定も使用します。</span><span class="sxs-lookup"><span data-stu-id="de217-113">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="de217-114">次のグローバル設定領域:</span><span class="sxs-lookup"><span data-stu-id="de217-114">These global settings area:</span></span>

- <span data-ttu-id="de217-115">[ **次の URL をブロックする] リスト** 。</span><span class="sxs-lookup"><span data-stu-id="de217-115">The **Block the following URLs** list.</span></span> <span data-ttu-id="de217-116">詳細については、「安全なリンク [」の「次の URL をブロックする」リストを参照してください。](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="de217-116">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="de217-117">365 のアプリOfficeリンク保護。</span><span class="sxs-lookup"><span data-stu-id="de217-117">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="de217-118">詳細については、「セーフ リンクの [設定」を参照Office 365 アプリを参照してください](atp-safe-links.md#safe-links-settings-for-office-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="de217-118">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="de217-119">グローバルセーフ リンクの設定は、セキュリティ & コンプライアンス センターまたは PowerShell で構成できます (Exchange Online のメールボックスを持つ対象となる Microsoft 365 組織の場合は Exchange Online PowerShell、Exchange Online メールボックスのない組織ではスタンドアロンの EOP PowerShell、Microsoft Defender for Office 365 アドオン サブスクリプション)。</span><span class="sxs-lookup"><span data-stu-id="de217-119">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="de217-120">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="de217-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="de217-121">セーフ リンクのグローバル設定によって提供される機能は、アクティブなセーフ リンク ポリシーに含まれるユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="de217-121">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="de217-122">組み込みまたは既定のセーフ リンク ポリシーはないので、これらのグローバル設定をアクティブにするには、少なくとも 1 つのセーフ リンク ポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de217-122">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="de217-123">手順については [、「Set up Safe Links policies in Microsoft Defender for Office 365」を参照してください](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="de217-123">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="de217-124"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="de217-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="de217-125">[安全なリンク] ページに **直接移動するには** 、 を使用します <https://protection.office.com/safelinksv2> 。</span><span class="sxs-lookup"><span data-stu-id="de217-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="de217-126">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de217-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="de217-127">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de217-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="de217-128">この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="de217-128">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="de217-129">セーフ リンクのグローバル設定を構成するには、組織の管理またはセキュリティ管理者の役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="de217-129">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="de217-130">セーフ リンクのグローバル設定への読み取り専用アクセスには、グローバル リーダーまたはセキュリティリーダーの役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="de217-130">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="de217-131">詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de217-131">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="de217-132">**注**:</span><span class="sxs-lookup"><span data-stu-id="de217-132">**Notes**:</span></span>

  - <span data-ttu-id="de217-133">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="de217-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="de217-134">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de217-134">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="de217-135">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="de217-135">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="de217-136">セーフ リンクのグローバル設定の推奨値については、「セーフ リンクの設定 [」を参照してください](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)。</span><span class="sxs-lookup"><span data-stu-id="de217-136">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span></span>

- <span data-ttu-id="de217-137">新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="de217-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="de217-138">[新しい機能は、Microsoft Defender に継続的に 365 Officeされています](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="de217-138">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="de217-139">新しい機能が追加された場合、既存のセーフ リンク ポリシーを調整する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="de217-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="de217-140">セキュリティ コンプライアンス センターで [次の URL をブロックする] &構成する</span><span class="sxs-lookup"><span data-stu-id="de217-140">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="de217-141">[ **次の URL をブロックする** ] リストは、サポートされているアプリのセーフ リンク スキャンによって常にブロックする必要があるリンクを識別します。</span><span class="sxs-lookup"><span data-stu-id="de217-141">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="de217-142">詳細については、「安全なリンク」の「次の URL をブロックする [」リストを参照してください](atp-safe-links.md#block-the-following-urls-list-for-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="de217-142">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="de217-143">セキュリティ コンプライアンス センターで&管理ポリシー ATPセーフ リンクに移動し、[グローバル \>  \> 設定]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="de217-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="de217-144">組織の **セーフ リンク ポリシーが表示されたら** 、[次の URL をブロックする] **ボックスに移動** します。</span><span class="sxs-lookup"><span data-stu-id="de217-144">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="de217-145">「次の URL をブロックする」リストのエントリ構文の説明に従って、1 つ以上の [エントリを構成します](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="de217-145">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="de217-146">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de217-146">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="de217-147">PowerShell で "次の URL をブロックする" リストを構成する</span><span class="sxs-lookup"><span data-stu-id="de217-147">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="de217-148">エントリの構文の詳細については、「次の URL をブロックする」リストの [エントリ構文を参照してください](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="de217-148">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="de217-149">**Get-AtpPolicyForO365** コマンドレットを使用して _、BlockURLs_ プロパティの既存のエントリを表示できます。</span><span class="sxs-lookup"><span data-stu-id="de217-149">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="de217-150">既存のエントリを置き換える値を追加するには、Exchange Online PowerShell または Exchange Online Protection PowerShell で次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="de217-150">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="de217-151">次の使用例は、次のエントリをリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="de217-151">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="de217-152">ドメイン、サブドメイン、およびパスをブロック fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="de217-152">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="de217-153">サブドメインの調査をブロックしますが、親ドメインや他のサブドメインはブロック tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="de217-153">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="de217-154">他の既存のエントリに影響を与えることなく値を追加または削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="de217-154">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="de217-155">次の使用例は、adatum.com の新しいエントリを追加し、そのエントリを fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="de217-155">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="de217-156">セキュリティ コンプライアンス センターで 365 Officeアプリの安全なリンク保護&構成する</span><span class="sxs-lookup"><span data-stu-id="de217-156">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="de217-157">365 のアプリOfficeの安全なリンク保護は、サポートされているデスクトップ、モバイル、および web アプリOfficeドキュメントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="de217-157">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="de217-158">詳細については、「セーフ リンクの [設定」を参照Office 365 アプリを参照してください](atp-safe-links.md#safe-links-settings-for-office-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="de217-158">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="de217-159">セキュリティ コンプライアンス センターで&管理ポリシー ATPセーフ リンクに移動し、[グローバル \>  \> 設定]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="de217-159">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="de217-160">組織の **セーフ リンク ポリシー** が表示されたら、[メール以外のコンテンツに適用される設定] セクションで次の **設定を構成** します。</span><span class="sxs-lookup"><span data-stu-id="de217-160">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="de217-161">**Office 365** アプリケーション: サポートされている 365 アプリの安全なリンクを有効にするには、トグルが右側 ![ Office確認してください。 ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="de217-161">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="de217-162">**ユーザー** が [安全なリンク] をクリックしても追跡しない: トグルを左に移動して、サポートされている Office 365 アプリのブロックされた URL に関連するユーザーのクリックを追跡します。トグルを ![ オフにします ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="de217-162">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="de217-163">**ユーザー** が元の URL への安全なリンクをクリックさせない: トグルが右にあることを確認して、ユーザーがサポートされている Office 365 アプリの元のブロックされた URL をクリックできない状態にします。トグルをオンにします。 ![ ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="de217-163">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="de217-164">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de217-164">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="de217-165">PowerShell で 365 のアプリOfficeリンク保護を構成する</span><span class="sxs-lookup"><span data-stu-id="de217-165">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="de217-166">PowerShell を使用して Office 365 アプリのセーフ リンク保護を構成する場合は、Exchange Online PowerShell または Exchange Online Protection PowerShell で次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="de217-166">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="de217-167">この例では、365 アプリのセーフ リンク保護のOffice構成します。</span><span class="sxs-lookup"><span data-stu-id="de217-167">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="de217-168">365 Office アプリの安全なリンクが有効になっています _(EnableSafeLinksForO365Clients_ パラメーターは使用していないので、既定値は$true)。</span><span class="sxs-lookup"><span data-stu-id="de217-168">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="de217-169">365 アプリのサポートされている URL に関連するユーザー Officeクリックが追跡されます。</span><span class="sxs-lookup"><span data-stu-id="de217-169">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="de217-170">ユーザーは、サポートされている Office 365 アプリの元のブロックされた URL をクリックすることはできません _(AllowClickThrough_ パラメーターは使用していないので、既定値は $false)。</span><span class="sxs-lookup"><span data-stu-id="de217-170">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="de217-171">構文とパラメーターの詳細については [、「Set-AtpPolicyForO365」を参照してください](/powershell/module/exchange/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="de217-171">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="de217-172">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="de217-172">How do you know these procedures worked?</span></span>

<span data-ttu-id="de217-173">セーフ リンクのグローバル設定 ([次の **URL** をブロックする] リストと Office 365 アプリ保護設定) が正常に構成されたことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="de217-173">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="de217-174">[セキュリティ & コンプライアンス センター] で、[脅威管理ポリシー ATP セーフ リンク] に移動し、[グローバル設定] をクリックして、表示されるフライアウトの設定 \>  \> を確認します。 </span><span class="sxs-lookup"><span data-stu-id="de217-174">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="de217-175">Exchange Online PowerShell または Exchange Online Protection PowerShell で、次のコマンドを実行し、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="de217-175">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="de217-176">構文とパラメーターの詳細については [、「Get-AtpPolicyForO365」を参照してください](/powershell/module/exchange/get-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="de217-176">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>