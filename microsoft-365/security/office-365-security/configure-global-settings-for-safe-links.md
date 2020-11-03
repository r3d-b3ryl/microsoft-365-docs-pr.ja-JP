---
title: Office 365 の Defender での安全なリンク設定のグローバル設定を構成する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、Microsoft Defender for Office 365 の「安全なリンク」のグローバル設定を表示および構成する方法について説明します (「Office 365 アプリの次の Url のリストと保護」を参照してください)。
ms.openlocfilehash: 655fba35bf3675bfd571c8e4923a00fbeba85304
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842430"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="7d455-103">Microsoft Defender for Office 365 の安全なリンクのグローバル設定を構成する</span><span class="sxs-lookup"><span data-stu-id="7d455-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="7d455-104">この記事は [、Microsoft Defender For Office 365 を](office-365-atp.md)使用しているビジネスのお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="7d455-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="7d455-105">Outlook の Safelinks に関する情報をお探しのホームユーザーの場合は、「 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d455-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="7d455-106">「安全なリンク」とは、メールフローで受信電子メールメッセージの URL スキャンを行う [Office 365 の](office-365-atp.md) 機能の1つであり、電子メールメッセージやその他の場所で url とリンクの確認をクリックしたときに表示されるものです。</span><span class="sxs-lookup"><span data-stu-id="7d455-106">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="7d455-107">詳細については、「 [Microsoft Defender For Office 365」](atp-safe-links.md)の「安全なリンク」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d455-107">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="7d455-108">[安全なリンク] ポリシーで、ほとんどの安全なリンクの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="7d455-108">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="7d455-109">手順については、「 [Set Up Safe Links policies In office 365](set-up-atp-safe-links-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d455-109">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

<span data-ttu-id="7d455-110">しかし、安全なリンクは、アクティブな安全リンクポリシーに含まれるすべてのユーザーに適用されるグローバル設定も使用します。</span><span class="sxs-lookup"><span data-stu-id="7d455-110">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="7d455-111">これらのグローバル設定領域:</span><span class="sxs-lookup"><span data-stu-id="7d455-111">These global settings area:</span></span>

- <span data-ttu-id="7d455-112">[ **次の url をブロック** する] の一覧。</span><span class="sxs-lookup"><span data-stu-id="7d455-112">The **Block the following URLs** list.</span></span> <span data-ttu-id="7d455-113">詳細については、 [「安全なリンク」の「次の url をブロックする」の一覧](atp-safe-links.md#block-the-following-urls-list-for-safe-links)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d455-113">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="7d455-114">Office 365 アプリの安全なリンク保護。</span><span class="sxs-lookup"><span data-stu-id="7d455-114">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="7d455-115">詳細については、「 [Office 365 アプリの安全なリンク設定](atp-safe-links.md#safe-links-settings-for-office-365-apps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d455-115">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="7d455-116">セキュリティ & コンプライアンスセンターまたは PowerShell (exchange online のメールボックスを使用する対象の Microsoft 365 組織用の Exchange Online PowerShell、exchange online メールボックスを持たない組織の場合はスタンドアロン EOP PowerShell、Office 365 アドオンサブスクリプションの場合は Microsoft Defender) で、グローバルな安全リンク設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="7d455-116">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7d455-117">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="7d455-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7d455-118">「安全なリンク」のグローバル設定で提供される機能は、アクティブな安全リンクポリシーに含まれているユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="7d455-118">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="7d455-119">組み込みまたは既定の安全なリンクポリシーはありません。そのため、これらのグローバル設定をアクティブにするには、少なくとも1つの安全なリンクポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d455-119">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="7d455-120">手順については、「 [Set Up Safe Links policies In office 365](set-up-atp-safe-links-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d455-120">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="7d455-121"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="7d455-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="7d455-122">[ **安全なリンク** ] ページに直接移動するには、を使用 <https://protection.office.com/safelinksv2> します。</span><span class="sxs-lookup"><span data-stu-id="7d455-122">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="7d455-123">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d455-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="7d455-124">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d455-124">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="7d455-125">安全なリンクのためのグローバル設定を表示および構成するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d455-125">To view and configure the global settings for Safe Links, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="7d455-126">**組織の管理** または [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の **セキュリティ管理者** 。</span><span class="sxs-lookup"><span data-stu-id="7d455-126">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="7d455-127">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)での **組織の管理** 。</span><span class="sxs-lookup"><span data-stu-id="7d455-127">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="7d455-128">「安全なリンク」の「グローバル設定」に推奨される値については、「 [安全なリンクの設定](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d455-128">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span></span>

- <span data-ttu-id="7d455-129">新規または更新されたポリシーが適用されるまで最大30分かかります。</span><span class="sxs-lookup"><span data-stu-id="7d455-129">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="7d455-130">[新しい機能は、Microsoft Defender For Office 365 に継続的に追加](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)されています。</span><span class="sxs-lookup"><span data-stu-id="7d455-130">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="7d455-131">新機能が追加されたときに、既存の安全なリンクポリシーを調整する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="7d455-131">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="7d455-132">セキュリティ & コンプライアンスセンターの [次の Url をブロックする] の一覧を構成する</span><span class="sxs-lookup"><span data-stu-id="7d455-132">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="7d455-133">[ **次の url をブロック** する] リストは、サポートされているアプリでの安全なリンクスキャンによって常にブロックされるリンクを示しています。</span><span class="sxs-lookup"><span data-stu-id="7d455-133">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="7d455-134">詳細については、 [「安全なリンク」の「次の url をブロックする」の一覧](atp-safe-links.md#block-the-following-urls-list-for-safe-links)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d455-134">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="7d455-135">[セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP セーフリンク** ] に移動し、[ **グローバル設定** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7d455-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links** , and then click **Global settings**.</span></span>

2. <span data-ttu-id="7d455-136">[ **組織の安全なリンク] ポリシー** が表示されたら、[ **次の url をブロック** する] ボックスに移動します。</span><span class="sxs-lookup"><span data-stu-id="7d455-136">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="7d455-137">[「次の url をブロックする」リストの「Entry 構文](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)」に記載されている1つ以上のエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="7d455-137">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="7d455-138">完了したら、 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7d455-138">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="7d455-139">PowerShell で [次の Url をブロックする] の一覧を構成する</span><span class="sxs-lookup"><span data-stu-id="7d455-139">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="7d455-140">エントリの構文の詳細については、 [「次の url をブロックする」のリストの「エントリの構文」](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d455-140">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="7d455-141">**AtpPolicyForO365** コマンドレットを使用して、 _blockurls_ プロパティの既存のエントリを表示できます。</span><span class="sxs-lookup"><span data-stu-id="7d455-141">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="7d455-142">既存のエントリを置き換える値を追加するには、Exchange Online PowerShell または Exchange Online Protection の PowerShell で次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="7d455-142">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="7d455-143">この例では、次のエントリをリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="7d455-143">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="7d455-144">Fabrikam.com のドメイン、サブドメイン、およびパスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="7d455-144">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="7d455-145">サブドメインの調査をブロックするが、tailspintoys.com で親ドメインまたは他のサブドメインをブロックする</span><span class="sxs-lookup"><span data-stu-id="7d455-145">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="7d455-146">他の既存のエントリに影響を及ぼさずに値を追加または削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="7d455-146">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="7d455-147">次の使用例は、adatum.com の新しいエントリを追加し、fabrikam.com のエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="7d455-147">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="7d455-148">セキュリティ & コンプライアンスセンターで Office 365 アプリの安全なリンク保護を構成する</span><span class="sxs-lookup"><span data-stu-id="7d455-148">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="7d455-149">安全なリンク保護 Office 365 アプリは、サポート対象の Office デスクトップ、モバイル、および web アプリのドキュメントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="7d455-149">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="7d455-150">詳細については、「 [Office 365 アプリの安全なリンク設定](atp-safe-links.md#safe-links-settings-for-office-365-apps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d455-150">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="7d455-151">[セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP セーフリンク** ] に移動し、[ **グローバル設定** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7d455-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links** , and then click **Global settings**.</span></span>

2. <span data-ttu-id="7d455-152">[ **組織の安全なリンク] ポリシー** が表示されたら、[ **電子メール以外のコンテンツに適用する設定** ] で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="7d455-152">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="7d455-153">**Office 365 アプリケーション** : サポートされている office 365 アプリの安全なリンクを有効にするには、[切り替え] が [オン] になっていることを確認します。 ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)</span><span class="sxs-lookup"><span data-stu-id="7d455-153">**Office 365 applications** : Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="7d455-154">**ユーザーが [安全なリンク] をクリックしたときに追跡しない** : サポートされている Office 365 アプリでブロックされる url に関連するユーザークリックを追跡するには、トグルをオフにします。 ![ ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="7d455-154">**Do not track when users click Safe Links** : Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="7d455-155">**ユーザーが元の URL に安全なリンクをクリックできない** ようにします。 [トグル] が [サポートされている Office 365 アプリの元のブロックする url] をクリックすると、[オン] に切り替えられないようにします。 ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)</span><span class="sxs-lookup"><span data-stu-id="7d455-155">**Do not let users click through Safe Links to the original URL** : Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   <span data-ttu-id="7d455-156">完了したら、 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7d455-156">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="7d455-157">PowerShell で Office 365 アプリの安全なリンク保護を構成する</span><span class="sxs-lookup"><span data-stu-id="7d455-157">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="7d455-158">PowerShell を使用して Office 365 アプリの安全なリンク保護を構成する場合は、Exchange Online PowerShell または Exchange Online Protection の PowerShell で次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="7d455-158">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="7d455-159">この例では、Office 365 アプリの安全なリンク保護について次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="7d455-159">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="7d455-160">Office 365 アプリの安全なリンクが有効になっています ( _EnableSafeLinksForO365Clients_ パラメーターは使用しておらず、既定値は $true)。</span><span class="sxs-lookup"><span data-stu-id="7d455-160">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="7d455-161">サポートされている Office 365 でブロックされている Url に関連するユーザークリックが追跡されます。</span><span class="sxs-lookup"><span data-stu-id="7d455-161">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="7d455-162">サポートされている Office 365 アプリの元のブロックされた URL をクリックすることはできません ( _allowclickthrough クリックスルー_ パラメーターは使用しておらず、既定値は $false)。</span><span class="sxs-lookup"><span data-stu-id="7d455-162">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="7d455-163">構文およびパラメーターの詳細については、「 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d455-163">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="7d455-164">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="7d455-164">How do you know these procedures worked?</span></span>

<span data-ttu-id="7d455-165">安全なリンクのグローバル設定が正常に構成されたことを確認するには ([ **次の url をブロック** する] と [Office 365 app protection] の設定)、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7d455-165">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="7d455-166">セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP セーフリンク** ] に移動し、[ **グローバル設定** ] をクリックして、画面上に表示される設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="7d455-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links** , click **Global settings** , and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="7d455-167">Exchange Online PowerShell または Exchange Online Protection PowerShell で、次のコマンドを実行し、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="7d455-167">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="7d455-168">構文およびパラメーターの詳細については、「 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d455-168">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>
