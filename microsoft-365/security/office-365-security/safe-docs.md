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
description: Microsoft 365 E5 または Microsoft 365 E5 セキュリティの安全なドキュメントについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 78ae99158e30046923d24897e7ab9b45adff31d0
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445398"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="09bae-103">Microsoft 365 E5 の安全なドキュメント</span><span class="sxs-lookup"><span data-stu-id="09bae-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="09bae-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="09bae-104">**Applies to**</span></span>
- [<span data-ttu-id="09bae-105">Microsoft Defender for Office 365 プラン 2</span><span class="sxs-lookup"><span data-stu-id="09bae-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="09bae-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="09bae-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="09bae-107">安全なドキュメントは、Microsoft 365 E5 または Microsoft 365 E5 セキュリティの機能で[、Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) [](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)を使用して、保護ビューまたは Application Guard for Office で開いているドキュメントとファイル[をスキャンします](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46)。</span><span class="sxs-lookup"><span data-stu-id="09bae-107">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) or [Application Guard for Office](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="09bae-108">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="09bae-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="09bae-109">安全なドキュメントは *、Microsoft 365 E5* または *Microsoft 365 E5 セキュリティ* ライセンスを持つユーザーにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="09bae-109">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="09bae-110">これらのライセンスは、Microsoft Defender の 365 プランOffice含まれていません。</span><span class="sxs-lookup"><span data-stu-id="09bae-110">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="09bae-111">安全なドキュメントは、Microsoft 365 Apps for enterprise (以前は Office 365 ProPlus) バージョン 2004 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="09bae-111">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="09bae-112"><https://protection.office.com> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="09bae-112">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="09bae-113">ATP の [安全な添付ファイル] ページ **に直接移動するには** 、 を開きます <https://protection.office.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="09bae-113">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="09bae-114">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09bae-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="09bae-115">この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="09bae-115">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="09bae-116">安全なドキュメント設定を構成するには、組織の管理またはセキュリティ管理者の役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="09bae-116">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="09bae-117">安全なドキュメント設定への読み取り専用アクセスでは、グローバル リーダーまたはセキュリティリーダーの役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="09bae-117">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="09bae-118">詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09bae-118">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="09bae-119">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="09bae-119">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="09bae-120">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09bae-120">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="09bae-121">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="09bae-121">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="09bae-122">Microsoft はデータを処理する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="09bae-122">How does Microsoft handle your data?</span></span>

<span data-ttu-id="09bae-123">保護を維持するために、セーフ ドキュメントは分析のために [Microsoft Defender for Endpoint クラウド](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) にファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="09bae-123">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="09bae-124">Microsoft Defender for Endpoint がデータを処理する方法の詳細については [、Microsoft Defender for Endpoint データストレージとプライバシーを参照してください](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。</span><span class="sxs-lookup"><span data-stu-id="09bae-124">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="09bae-125">安全なドキュメントによって送信されたファイルは、分析に必要な時間を超えて Defender に保持されません (通常、24 時間未満)。</span><span class="sxs-lookup"><span data-stu-id="09bae-125">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="09bae-126">セキュリティ コンプライアンス センター&使用して安全なドキュメントを構成する</span><span class="sxs-lookup"><span data-stu-id="09bae-126">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="09bae-127">セキュリティ セキュリティ コンプライアンス センター&に移動し、[**脅威管理ポリシー** ATP の安全な添付ファイル] に移動し、[ \>  \> グローバル設定]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="09bae-127">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="09bae-128">[グローバル **設定] が** 表示されたら、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="09bae-128">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="09bae-129">**[クライアントの安全な** ドキュメントOfficeする: トグルを右に移動して機能を有効にする: ![ トグルをオンにします ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="09bae-129">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="09bae-130">**安全なドキュメント** でファイルが悪意のあるファイルとして識別された場合でも、保護されたビューをクリックすることを許可する: このオプションをオフのままにすることをお勧めします (トグルは左 ![ に切り替えます。 ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="09bae-130">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="09bae-131">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09bae-131">When you're finished, click **Save**.</span></span>

   ![[安全な添付ファイル] ページで [グローバル設定] を選択した後の安全なドキュメントの設定。](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="09bae-133">Exchange Online PowerShell を使用して安全なドキュメントを構成する</span><span class="sxs-lookup"><span data-stu-id="09bae-133">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="09bae-134">次の構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="09bae-134">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="09bae-135">_EnableSafeDocs パラメーター_ は、組織全体の安全なドキュメントを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="09bae-135">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="09bae-136">_AllowSafeDocsOpen_ パラメーターは、ドキュメントが悪意のあると識別された場合に、ユーザーが保護されたビューを離れる (つまり、ドキュメントを開く) のを許可または防止します。</span><span class="sxs-lookup"><span data-stu-id="09bae-136">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="09bae-137">この例では、組織全体で安全なドキュメントを有効にし、ユーザーが保護されたビューから悪意のあると識別されたドキュメントを開くのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="09bae-137">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="09bae-138">構文とパラメーターの詳細については [、「Set-AtpPolicyForO365」を参照してください](/powershell/module/exchange/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="09bae-138">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a><span data-ttu-id="09bae-139">Microsoft Defender for Endpoint Service にオンボードして監査機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="09bae-139">Onboard to the Microsoft Defender for Endpoint Service to enable auditing capabilities</span></span>

<span data-ttu-id="09bae-140">Microsoft Defender for Endpoint を展開するには、展開のさまざまなフェーズを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09bae-140">To deploy Microsoft Defender for Endpoint, you need to go through the various phases of deployment.</span></span> <span data-ttu-id="09bae-141">オンボーディング後、コンプライアンス センターのセキュリティ サーバーで監査&構成できます。</span><span class="sxs-lookup"><span data-stu-id="09bae-141">After onboarding, you can configure auditing capabilities in the Security & Compliance Center.</span></span>

<span data-ttu-id="09bae-142">詳細については [、「Onboard to the Microsoft Defender for Endpoint service」を参照してください](/microsoft-365/security/defender-endpoint/onboarding)。</span><span class="sxs-lookup"><span data-stu-id="09bae-142">To learn more, see [Onboard to the Microsoft Defender for Endpoint service](/microsoft-365/security/defender-endpoint/onboarding).</span></span> <span data-ttu-id="09bae-143">その他のヘルプが必要な場合は [、「Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング」を参照してください](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)。</span><span class="sxs-lookup"><span data-stu-id="09bae-143">If you need additional help, please refer to [Troubleshoot Microsoft Defender for Endpoint onboarding issues](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="09bae-144">設定が適用されたことを確認する方法</span><span class="sxs-lookup"><span data-stu-id="09bae-144">How do I know this worked?</span></span>

<span data-ttu-id="09bae-145">セーフ ドキュメントを有効にし、構成したことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="09bae-145">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="09bae-146">セキュリティ & コンプライアンス センターで、[脅威管理ポリシー ATP の安全な添付ファイル] に移動し、[グローバル設定] をクリックし \>  \> **、[Office** クライアントの安全なドキュメントを有効にする] と [安全なドキュメントが悪意のある設定としてファイルを識別した場合でも、保護されたビューをクリックするユーザーを許可する] を確認します。</span><span class="sxs-lookup"><span data-stu-id="09bae-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="09bae-147">Exchange Online PowerShell で次のコマンドを実行し、プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="09bae-147">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="09bae-148">安全なドキュメント保護をテストするには、次のファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="09bae-148">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="09bae-149">これらのドキュメントは、マルウェア対策EICAR.TXTウイルス対策ソリューションをテストするファイルと似ています。</span><span class="sxs-lookup"><span data-stu-id="09bae-149">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="09bae-150">ファイルは有害ではないが、安全なドキュメント保護をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="09bae-150">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="09bae-151">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="09bae-151">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="09bae-152">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="09bae-152">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="09bae-153">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="09bae-153">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
