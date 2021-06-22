---
title: Microsoft Defender for Office 365 の安全なドキュメント
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 詳細については、「セーフドキュメント」または「Microsoft 365 E5」をMicrosoft 365 E5 Security。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1049543b11ad14eeeed596367228f025cc8edd65
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054430"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="4afe3-103">Microsoft 365 E5 の安全なドキュメント</span><span class="sxs-lookup"><span data-stu-id="4afe3-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4afe3-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="4afe3-104">**Applies to**</span></span>
- [<span data-ttu-id="4afe3-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4afe3-105">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="4afe3-106">セーフドキュメントは Microsoft 365 E5 または Microsoft 365 E5 Security の機能で[、Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)を使用して、保護ビューまたは Application Guard[](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)で開いている[](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46)ドキュメントとファイルをスキャンOffice。</span><span class="sxs-lookup"><span data-stu-id="4afe3-106">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) or [Application Guard for Office](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4afe3-107">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="4afe3-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4afe3-108">セーフドキュメントは、ライセンスまたはライセンスを持 *Microsoft 365 E5ユーザー* *Microsoft 365 E5 Security* 使用できます。</span><span class="sxs-lookup"><span data-stu-id="4afe3-108">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="4afe3-109">これらのライセンスは、Microsoft Defender のプランに含Office 365ではありません。</span><span class="sxs-lookup"><span data-stu-id="4afe3-109">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="4afe3-110">セーフドキュメントは、Microsoft 365 Apps for enterprise (以前は Office 365 ProPlus) バージョン 2004 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4afe3-110">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="4afe3-111"><https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4afe3-111">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="4afe3-112">[添付ファイル] ページに **直接移動セーフを** 使用します <https://security.microsoft.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="4afe3-112">To go directly to the **Safe Attachments** page, use <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="4afe3-113">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4afe3-113">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="4afe3-114">この記事の **手順をExchange Online** 前に、アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="4afe3-114">You need permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="4afe3-115">ドキュメントのセーフ構成するには、組織の管理役割グループまたはセキュリティ管理者役割グループ **のメンバーである** 必要があります。 </span><span class="sxs-lookup"><span data-stu-id="4afe3-115">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="4afe3-116">ドキュメント設定への読み取りセーフアクセスするには、グローバル リーダーまたはセキュリティ リーダーの役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="4afe3-116">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="4afe3-117">詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4afe3-117">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="4afe3-118">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="4afe3-118">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="4afe3-119">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4afe3-119">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="4afe3-120">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="4afe3-120">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="4afe3-121">Microsoft はデータを処理する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="4afe3-121">How does Microsoft handle your data?</span></span>

<span data-ttu-id="4afe3-122">保護を維持するために、セーフドキュメントは分析のために[Microsoft Defender for Endpoint クラウド](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)にファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="4afe3-122">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="4afe3-123">Microsoft Defender for Endpoint がデータを処理する方法の詳細については [、Microsoft Defender for Endpoint データストレージとプライバシーを参照してください](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。</span><span class="sxs-lookup"><span data-stu-id="4afe3-123">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="4afe3-124">ドキュメントから送信セーフは、分析に必要な時間 (通常は 24 時間未満) を超えて Defender に保持されません。</span><span class="sxs-lookup"><span data-stu-id="4afe3-124">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-microsoft-365-defender-to-configure-safe-documents"></a><span data-ttu-id="4afe3-125">ドキュメントを構成Microsoft 365 Defenderするには、セーフを使用します。</span><span class="sxs-lookup"><span data-stu-id="4afe3-125">Use the Microsoft 365 Defender to configure Safe Documents</span></span>

1. <span data-ttu-id="4afe3-126">[メール] Microsoft 365 Defenderを開き、[メール &**ポリシー** ] &[脅威ポリシーポリシー] セクションの [添付ファイル] に \>  \>  \>  \> **セーフします**。</span><span class="sxs-lookup"><span data-stu-id="4afe3-126">Open the Microsoft 365 Defender portal and go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="4afe3-127">[添付ファイル **セーフ] ページで**、[グローバル設定]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4afe3-127">On the **Safe Attachments** page, click **Global settings**.</span></span>

3. <span data-ttu-id="4afe3-128">[グローバル **設定] が** 表示されたら、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="4afe3-128">In the **Global settings** fly out that appears, configure the following settings:</span></span>
   - <span data-ttu-id="4afe3-129">**[クライアントセーフドキュメントOfficeオン** にする: トグルを右に移動して機能を有効にします。トグルを ![ オンにします ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="4afe3-129">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>
   - <span data-ttu-id="4afe3-130">**セーフ ドキュメント** がファイルを悪意のあるファイルと特定した場合でも、保護されたビューをクリックすることを許可する: このオプションはオフのままにすることをお勧めします (トグルは左に切り替えます。 ![ ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="4afe3-130">**Allow people to click through Protected View even if Safe Documents identified the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="4afe3-131">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4afe3-131">When you're finished, click **Save**.</span></span>

   ![セーフ[添付ファイル] ページで [グローバル設定] を選択した後セーフ設定します。](../../media/safe-docs-global-settings.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="4afe3-133">PowerShell Exchange Onlineを使用してドキュメントセーフ構成する</span><span class="sxs-lookup"><span data-stu-id="4afe3-133">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="4afe3-134">次の構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="4afe3-134">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="4afe3-135">_EnableSafeDocs パラメーターは_、組織全体セーフドキュメントを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="4afe3-135">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="4afe3-136">_AllowSafeDocsOpen_ パラメーターは、ドキュメントが悪意のあると識別された場合に、ユーザーが保護されたビューを離れる (つまり、ドキュメントを開く) のを許可または防止します。</span><span class="sxs-lookup"><span data-stu-id="4afe3-136">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="4afe3-137">この例では、セーフドキュメントの削除を有効にし、保護されたビューから悪意のあると識別されたドキュメントを開くユーザーを防止します。</span><span class="sxs-lookup"><span data-stu-id="4afe3-137">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="4afe3-138">構文とパラメーターの詳細については [、「Set-AtpPolicyForO365」を参照してください](/powershell/module/exchange/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="4afe3-138">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a><span data-ttu-id="4afe3-139">Microsoft Defender for Endpoint Service にオンボードして監査機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="4afe3-139">Onboard to the Microsoft Defender for Endpoint Service to enable auditing capabilities</span></span>

<span data-ttu-id="4afe3-140">Microsoft Defender for Endpoint を展開するには、展開のさまざまなフェーズを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4afe3-140">To deploy Microsoft Defender for Endpoint, you need to go through the various phases of deployment.</span></span> <span data-ttu-id="4afe3-141">オンボーディングの後、監査機能をポータルで構成Microsoft 365 Defenderできます。</span><span class="sxs-lookup"><span data-stu-id="4afe3-141">After onboarding, you can configure auditing capabilities in the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="4afe3-142">詳細については [、「Onboard to the Microsoft Defender for Endpoint service」を参照してください](/microsoft-365/security/defender-endpoint/onboarding)。</span><span class="sxs-lookup"><span data-stu-id="4afe3-142">To learn more, see [Onboard to the Microsoft Defender for Endpoint service](/microsoft-365/security/defender-endpoint/onboarding).</span></span> <span data-ttu-id="4afe3-143">その他のヘルプが必要な場合は、「Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング [」を参照してください](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)。</span><span class="sxs-lookup"><span data-stu-id="4afe3-143">If you need additional help, refer to [Troubleshoot Microsoft Defender for Endpoint onboarding issues](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="4afe3-144">設定が適用されたことを確認する方法</span><span class="sxs-lookup"><span data-stu-id="4afe3-144">How do I know this worked?</span></span>

<span data-ttu-id="4afe3-145">ドキュメントを有効にし、構成セーフするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4afe3-145">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="4afe3-146">Microsoft 365 Defender ポータルで、[メール **&** コラボレーション ポリシー & ルール 脅威ポリシー ポリシー] セクション セーフ 添付ファイルグローバル設定] に移動し \>  \>  \>  \>  \> **、[Office** クライアントの セーフ ドキュメントを有効にする] と [セーフ ドキュメントがファイルを悪意のある設定として識別した場合でも、保護されたビューをクリックするユーザーを許可する] を確認します。</span><span class="sxs-lookup"><span data-stu-id="4afe3-146">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments** \> **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="4afe3-147">PowerShell で次のコマンドをExchange Onlineし、プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="4afe3-147">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="4afe3-148">ドキュメント保護をテストするには、次セーフ使用できます。</span><span class="sxs-lookup"><span data-stu-id="4afe3-148">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="4afe3-149">これらのドキュメントは、マルウェア対策EICAR.TXTウイルス対策ソリューションをテストするファイルと似ています。</span><span class="sxs-lookup"><span data-stu-id="4afe3-149">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="4afe3-150">ファイルは有害ではないが、ドキュメント保護セーフトリガーします。</span><span class="sxs-lookup"><span data-stu-id="4afe3-150">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="4afe3-151">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="4afe3-151">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="4afe3-152">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="4afe3-152">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="4afe3-153">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="4afe3-153">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
