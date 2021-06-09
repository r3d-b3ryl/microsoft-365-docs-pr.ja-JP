---
title: Defender の [リンク] セーフのグローバル設定を構成Office 365
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
description: 管理者は、Microsoft Defender for Office 365 の セーフ リンクのグローバル設定 ([次の URL をブロックする] リストと Office 365 アプリの保護) を表示および構成する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4e77373657d3167ca8f5bafa544923ab3a2320ce
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821987"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="354d1-103">Microsoft Defender の [リンク] セーフのグローバル設定を構成するOffice 365</span><span class="sxs-lookup"><span data-stu-id="354d1-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="354d1-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="354d1-104">**Applies to**</span></span>
- [<span data-ttu-id="354d1-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="354d1-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="354d1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="354d1-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="354d1-107">この記事は、[Microsoft Defender for Office 365](defender-for-office-365.md) をご利用の法人のお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="354d1-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="354d1-108">セーフリンクに関する情報を探しているホーム ユーザーの場合は、「Advanced [Outlook Outlook.com セキュリティ」を参照してください](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="354d1-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="354d1-109">セーフ[リンクは、Microsoft Defender for Office 365](defender-for-office-365.md)の機能で、メール フロー内の受信電子メール メッセージの URL スキャン、および電子メール メッセージ内の URL とリンクのクリック検証の時間を提供します。</span><span class="sxs-lookup"><span data-stu-id="354d1-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="354d1-110">詳細については[、「Microsoft Defender セーフリンク」を参照Office 365。](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="354d1-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="354d1-111">[リンク] ポリシーでセーフリンクの設定セーフ構成します。</span><span class="sxs-lookup"><span data-stu-id="354d1-111">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="354d1-112">手順については、「Microsoft Defender for セーフのリンク ポリシーをセットアップする[」を参照Office 365。](set-up-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="354d1-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

<span data-ttu-id="354d1-113">ただし、セーフリンクは、リンク ポリシー自体の外部で構成する次セーフ設定も使用します。</span><span class="sxs-lookup"><span data-stu-id="354d1-113">But, Safe Links also uses the following global settings that you configure outside of the Safe Links policies themselves:</span></span>

- <span data-ttu-id="354d1-114">[ **次の URL をブロックする] リスト** 。</span><span class="sxs-lookup"><span data-stu-id="354d1-114">The **Block the following URLs** list.</span></span> <span data-ttu-id="354d1-115">この設定は、アクティブなリンク ポリシーに含まれるすべてのセーフ適用されます。</span><span class="sxs-lookup"><span data-stu-id="354d1-115">This setting applies to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="354d1-116">詳細については、「リンク」の「次の URL をブロックする[」をセーフしてください。](safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="354d1-116">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="354d1-117">セーフアプリのリンク保護Office 365します。</span><span class="sxs-lookup"><span data-stu-id="354d1-117">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="354d1-118">これらの設定は、ユーザーがアクティブな セーフ リンク ポリシーに含まれているかどうかに関係なく、Office 365 の Defender のライセンスを取得している組織内のすべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="354d1-118">These settings apply to all users in the organization who are licensed for Defender for Office 365, regardless of whether the users are included in active Safe Links policies or not.</span></span> <span data-ttu-id="354d1-119">詳細については、「アプリの[リンクセーフ設定」をOffice 365してください](safe-links.md#safe-links-settings-for-office-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="354d1-119">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="354d1-120">Microsoft 365 セキュリティ センターまたは PowerShell (Exchange Online PowerShell で、Exchange Online のメールボックスを持つ対象の Microsoft 365 組織、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell、microsoft Defender for Office 365 アドオン サブスクリプション) でグローバル セーフ リンク設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="354d1-120">You can configure the global Safe Links settings in the Microsoft 365 security center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="354d1-121">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="354d1-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="354d1-122">組み込みまたは既定の セーフ リンク ポリシーはないので、[次の URL をブロックする] リストをアクティブにするには、少なくとも 1 つの セーフ リンク ポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="354d1-122">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for the **Block the following URLs** list to be active.</span></span> <span data-ttu-id="354d1-123">手順については、「Microsoft Defender for セーフのリンク ポリシーをセットアップする[」を参照Office 365。](set-up-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="354d1-123">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

- <span data-ttu-id="354d1-124"><https://security.microsoft.com> でセキュリティ センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="354d1-124">You open the security center at <https://security.microsoft.com>.</span></span> <span data-ttu-id="354d1-125">[リンク] ページに直接 **移動セーフを** 使用します <https://security.microsoft.com/safelinksv2> 。</span><span class="sxs-lookup"><span data-stu-id="354d1-125">To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2>.</span></span>

- <span data-ttu-id="354d1-126">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="354d1-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="354d1-127">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="354d1-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="354d1-128">この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="354d1-128">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="354d1-129">リンクのグローバル設定を構成セーフ、組織の管理またはセキュリティ管理者の役割グループ **のメンバーである** 必要があります。 </span><span class="sxs-lookup"><span data-stu-id="354d1-129">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="354d1-130">リンクのグローバル設定への読み取り専用アクセスセーフ、グローバル リーダーまたはセキュリティ リーダーの役割グループのメンバー **である必要があります**。</span><span class="sxs-lookup"><span data-stu-id="354d1-130">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="354d1-131">詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="354d1-131">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="354d1-132">**注**:</span><span class="sxs-lookup"><span data-stu-id="354d1-132">**Notes**:</span></span>

  - <span data-ttu-id="354d1-133">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="354d1-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="354d1-134">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="354d1-134">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="354d1-135">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="354d1-135">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="354d1-136">リンクのグローバル設定の推奨値については、「セーフリンクのセーフ[を参照してください](recommended-settings-for-eop-and-office365.md#safe-links-settings)。</span><span class="sxs-lookup"><span data-stu-id="354d1-136">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365.md#safe-links-settings).</span></span>

- <span data-ttu-id="354d1-137">新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="354d1-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="354d1-138">[新しい機能は、Microsoft Defender](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)に継続的に追加Office 365。</span><span class="sxs-lookup"><span data-stu-id="354d1-138">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="354d1-139">新しい機能が追加された場合、既存のリンク ポリシーを調整するセーフがあります。</span><span class="sxs-lookup"><span data-stu-id="354d1-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security-center"></a><span data-ttu-id="354d1-140">セキュリティ センターで [次の URL をブロックする] リストを構成する</span><span class="sxs-lookup"><span data-stu-id="354d1-140">Configure the "Block the following URLs" list in the security center</span></span>

<span data-ttu-id="354d1-141">[**次の URL をブロックする**] ボックスの一覧は、サポートされているアプリの [リンクセーフによって常にブロックする必要があるリンクを識別します。</span><span class="sxs-lookup"><span data-stu-id="354d1-141">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="354d1-142">詳細については、「リンク」の「次の URL をブロックする[」をセーフしてください](safe-links.md#block-the-following-urls-list-for-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="354d1-142">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="354d1-143">セキュリティ センターで、[電子メール &**グループ**&ルールの脅威ポリシー] セクションに移動し、[リンク \>  \>  \>  \> **セーフします**。</span><span class="sxs-lookup"><span data-stu-id="354d1-143">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="354d1-144">[リンクの **セーフ] ページで**、[グローバル設定]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="354d1-144">On the **Safe Links** page, click **Global settings**.</span></span> <span data-ttu-id="354d1-145">組織の **セーフが表示されたら、[** 次の URL をブロックする]**ボックスに移動** します。</span><span class="sxs-lookup"><span data-stu-id="354d1-145">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="354d1-146">「次の URL をブロックする」リストのエントリ構文の説明に従って、1 つ以上の [エントリを構成します](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="354d1-146">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="354d1-147">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="354d1-147">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="354d1-148">PowerShell で "次の URL をブロックする" リストを構成する</span><span class="sxs-lookup"><span data-stu-id="354d1-148">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="354d1-149">エントリの構文の詳細については、「次の URL をブロックする」リストの [エントリ構文を参照してください](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="354d1-149">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="354d1-150">**Get-AtpPolicyForO365** コマンドレットを使用して _、BlockURLs_ プロパティの既存のエントリを表示できます。</span><span class="sxs-lookup"><span data-stu-id="354d1-150">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="354d1-151">既存のエントリを置き換える値を追加するには、PowerShell または PowerShell でExchange Online構文Exchange Online Protectionします。</span><span class="sxs-lookup"><span data-stu-id="354d1-151">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="354d1-152">次の使用例は、次のエントリをリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="354d1-152">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="354d1-153">ドメイン、サブドメイン、およびパスをブロック fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="354d1-153">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="354d1-154">サブドメインの調査をブロックしますが、親ドメインや他のサブドメインはブロック tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="354d1-154">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="354d1-155">他の既存のエントリに影響を与えることなく値を追加または削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="354d1-155">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="354d1-156">次の使用例は、adatum.com の新しいエントリを追加し、そのエントリを fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="354d1-156">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security-center"></a><span data-ttu-id="354d1-157">セキュリティ センターセーフアプリOffice 365リンク保護を構成する</span><span class="sxs-lookup"><span data-stu-id="354d1-157">Configure Safe Links protection for Office 365 apps in the security center</span></span>

<span data-ttu-id="354d1-158">セーフデスクトップ アプリ、モバイル Office 365 Web アプリでサポートされているドキュメントOfficeリンク保護が適用されます。</span><span class="sxs-lookup"><span data-stu-id="354d1-158">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="354d1-159">詳細については、「アプリの[リンクセーフ設定」をOffice 365してください](safe-links.md#safe-links-settings-for-office-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="354d1-159">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="354d1-160">セキュリティ センターで、[電子メール &**グループ**&ルールの脅威ポリシー] セクションに移動し、[リンク \>  \>  \>  \> **セーフします**。</span><span class="sxs-lookup"><span data-stu-id="354d1-160">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="354d1-161">[リンクの **セーフ] ページで**、[グローバル設定]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="354d1-161">On the **Safe Links** page, click **Global settings**.</span></span> <span data-ttu-id="354d1-162">組織の **セーフリンク** ポリシーが表示されたら、[サポートされているアプリ] セクションのコンテンツに適用される 設定 で次の **設定Office 365構成** します。</span><span class="sxs-lookup"><span data-stu-id="354d1-162">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content in supported Office 365 apps** section:</span></span>

   - <span data-ttu-id="354d1-163">**[セーフ アプリOffice 365リンク** を使用する: トグルが右にあるか確認して、サポートされているアプリの セーフ リンクを有効にする: Office 365オンに ![ 切り替える ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="354d1-163">**Use Safe Links in Office 365 apps**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="354d1-164">**ユーザー** が Office 365 アプリで保護されたリンクをクリックした場合は追跡しない: トグルを左に移動して、サポートされている Office 365 アプリのブロックされた URL に関連するユーザークリックを追跡します。トグルをオフ ![ にします。 ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="354d1-164">**Do not track when users click protected links in Office 365 apps**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="354d1-165">**ユーザー** が Office 365 アプリの元の URL をクリックさせない: トグルが右に表示され、サポートされている Office 365 アプリの元のブロックされた URL にユーザーがクリックスルーされるのを防ぐための確認: オンに切り替える ![ ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="354d1-165">**Do not let users click through to the original URL in Office 365 apps**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="354d1-166">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="354d1-166">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="354d1-167">PowerShell セーフアプリのリンク保護Office 365構成する</span><span class="sxs-lookup"><span data-stu-id="354d1-167">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="354d1-168">powerShell を使用して Office 365 アプリの セーフ リンク保護を構成する場合は、Exchange Online PowerShell または PowerShell で次Exchange Online Protectionします。</span><span class="sxs-lookup"><span data-stu-id="354d1-168">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="354d1-169">この例では、アプリ内のリンク保護セーフ設定をOffice 365します。</span><span class="sxs-lookup"><span data-stu-id="354d1-169">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="354d1-170">セーフアプリのOffice 365がオンになっています _(EnableSafeLinksForO365Clients_ パラメーターは使用していないので、既定値は有効$true)。</span><span class="sxs-lookup"><span data-stu-id="354d1-170">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="354d1-171">サポートされているアプリのブロックされた URL に関連Office 365クリックが追跡されます。</span><span class="sxs-lookup"><span data-stu-id="354d1-171">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="354d1-172">ユーザーは、サポートされている Office 365 アプリの元のブロックされた URL をクリックすることはできません _(AllowClickThrough_ パラメーターは使用していないので、既定値は $false)。</span><span class="sxs-lookup"><span data-stu-id="354d1-172">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="354d1-173">構文とパラメーターの詳細については [、「Set-AtpPolicyForO365」を参照してください](/powershell/module/exchange/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="354d1-173">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="354d1-174">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="354d1-174">How do you know these procedures worked?</span></span>

<span data-ttu-id="354d1-175">セーフ リンクのグローバル設定が正常に構成されたことを確認するには ([次のURL リストと Office 365 アプリ保護設定をブロックする] をクリックして、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="354d1-175">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="354d1-176">セキュリティ センターで、[メール **& コラボレーション** ポリシー& ルール脅威ポリシー] セクション \>  \>  \>  \> **セーフ** \> [グローバル設定] をクリックし、表示されるフライアウトの設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="354d1-176">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links** \> click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="354d1-177">PowerShell Exchange Onlineまたは PowerShell Exchange Online Protectionで、次のコマンドを実行し、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="354d1-177">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="354d1-178">構文とパラメーターの詳細については [、「Get-AtpPolicyForO365」を参照してください](/powershell/module/exchange/get-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="354d1-178">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>
