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
ms.openlocfilehash: a3f4ed3535c7e53774b9b567b50f7c06e99cef9d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288587"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="c5436-103">Microsoft 365 E5 の安全なドキュメント</span><span class="sxs-lookup"><span data-stu-id="c5436-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c5436-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="c5436-104">**Applies to**</span></span>
- [<span data-ttu-id="c5436-105">Microsoft Defender for Office 365 プラン 2</span><span class="sxs-lookup"><span data-stu-id="c5436-105">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="c5436-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c5436-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="c5436-107">安全なドキュメントは、Microsoft 365 E5 または Microsoft 365 E5 セキュリティの機能で[、Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)を使用して、保護ビューで開いているドキュメントやファイルをスキャン[します。](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)</span><span class="sxs-lookup"><span data-stu-id="c5436-107">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c5436-108">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="c5436-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c5436-109">安全なドキュメントは *、Microsoft 365 E5* または *Microsoft 365 E5 セキュリティ* ライセンスを持つユーザーだけが利用できます。</span><span class="sxs-lookup"><span data-stu-id="c5436-109">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="c5436-110">これらのライセンスは、Office 365 プランの Microsoft Defender には含まれていません。</span><span class="sxs-lookup"><span data-stu-id="c5436-110">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="c5436-111">安全なドキュメントは、Microsoft 365 Apps for enterprise (以前の Office 365 ProPlus) バージョン 2004 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c5436-111">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="c5436-112"><https://protection.office.com> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="c5436-112">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="c5436-113">[ATP の安全な添付ファイル **] ページに直接移動するには** 、開きます <https://protection.office.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="c5436-113">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="c5436-114">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5436-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="c5436-115">この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります:</span><span class="sxs-lookup"><span data-stu-id="c5436-115">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="c5436-116">安全なドキュメントの設定を構成するには、組織の管理役割グループまたはセキュリティ管理者役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5436-116">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="c5436-117">安全なドキュメントの設定に読み取り専用でアクセスするには、グローバル閲覧者またはセキュリティ閲覧者の役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5436-117">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="c5436-118">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5436-118">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="c5436-119">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="c5436-119">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="c5436-120">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5436-120">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="c5436-121">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="c5436-121">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="c5436-122">Microsoft はデータを処理する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="c5436-122">How does Microsoft handle your data?</span></span>

<span data-ttu-id="c5436-123">保護された状態を維持するために、安全なドキュメントは分析のために [Microsoft Defender for Endpoint クラウド](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) にファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="c5436-123">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="c5436-124">Microsoft Defender for Endpoint がデータを処理する方法の詳細については、Microsoft Defender for Endpoint のデータストレージとプライバシーに関するページ [をご覧ください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。</span><span class="sxs-lookup"><span data-stu-id="c5436-124">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="c5436-125">安全なドキュメントによって送信されたファイルは、分析に必要な時間を超えて Defender に保持されません (通常、24 時間未満)。</span><span class="sxs-lookup"><span data-stu-id="c5436-125">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="c5436-126">セキュリティ/コンプライアンス センター&使用して安全なドキュメントを構成する</span><span class="sxs-lookup"><span data-stu-id="c5436-126">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="c5436-127">セキュリティ/コンプライアンス センター&、**脅威管理** ポリシー ATP の安全な添付ファイルに移動し、[グローバル設定] \>  \> を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="c5436-127">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="c5436-128">表示される **グローバル設定** のフライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="c5436-128">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c5436-129">**[安全な** ドキュメント] を Officeクライアントに対して有効にする: トグルを右に移動して機能を有効にします。オンに切り ![ 替えます ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="c5436-129">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="c5436-130">**安全な** ドキュメントでファイルが悪意のあるものとして識別された場合でも、保護ビューをクリックすることを許可します。このオプションはオフのままにすることをお勧めします (左側のトグルをオフのままに ![ します ](../../media/scc-toggle-off.png) )。</span><span class="sxs-lookup"><span data-stu-id="c5436-130">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="c5436-131">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5436-131">When you're finished, click **Save**.</span></span>

   ![[安全な添付ファイル] ページで [グローバル設定] を選択した後の安全なドキュメントの設定。](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="c5436-133">Exchange Online PowerShell を使用して安全なドキュメントを構成する</span><span class="sxs-lookup"><span data-stu-id="c5436-133">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="c5436-134">次の構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="c5436-134">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="c5436-135">_EnableSafeDocs パラメーターは_、組織全体の安全なドキュメントを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="c5436-135">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="c5436-136">_AllowSafeDocsOpen_ パラメーターは、ドキュメントが悪意のあるものとして識別された場合に、ユーザーが保護ビューを離れる (つまり、ドキュメントを開く) のを許可または防止します。</span><span class="sxs-lookup"><span data-stu-id="c5436-136">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="c5436-137">この例では、組織全体に対して安全なドキュメントを有効にし、悪意のあるドキュメントとして識別されたドキュメントを保護ビューからユーザーが開くのを防止します。</span><span class="sxs-lookup"><span data-stu-id="c5436-137">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="c5436-138">構文およびパラメーターの詳細については [、「Set-AtpPolicyForO365」を参照](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)してください。</span><span class="sxs-lookup"><span data-stu-id="c5436-138">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="c5436-139">設定が適用されたことを確認する方法</span><span class="sxs-lookup"><span data-stu-id="c5436-139">How do I know this worked?</span></span>

<span data-ttu-id="c5436-140">安全なドキュメントを有効にし、構成されていることを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c5436-140">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="c5436-141">セキュリティ & コンプライアンス センターで、脅威管理ポリシー ATP の安全な添付ファイルに移動し、[グローバル設定] をクリックして \>  \> **、Office** クライアントの安全なドキュメントを有効にし、安全なドキュメントでファイルが悪意のある設定として識別された場合でも、保護ビューをクリックできるユーザーを許可します。</span><span class="sxs-lookup"><span data-stu-id="c5436-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="c5436-142">Exchange Online PowerShell で次のコマンドを実行し、プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="c5436-142">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="c5436-143">安全なドキュメント保護をテストするには、次のファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c5436-143">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="c5436-144">これらのドキュメントは、マルウェア対策EICAR.TXTウイルス対策ソリューションをテストする目的で使用されるファイルと似ています。</span><span class="sxs-lookup"><span data-stu-id="c5436-144">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="c5436-145">ファイルは有害ではないが、安全なドキュメント保護をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="c5436-145">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="c5436-146">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="c5436-146">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="c5436-147">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="c5436-147">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="c5436-148">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="c5436-148">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
